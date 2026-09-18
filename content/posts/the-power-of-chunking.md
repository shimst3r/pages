+++
date = '2026-09-18T20:52:33+02:00'
draft = false
title = 'The Power of Chunking'
+++

At my first job, I accidentally deleted three months worth of capacity planning. Lucky me, it was in March 2020 and capacity planning for that year was obsolete soon enough[^1].

I was refactoring large parts of the [ETL](https://en.wikipedia.org/wiki/Extract,_transform,_load) pipeline used to ingest the capacity data from our SaaS solution. It looked something like this:

```python
async def fetch_records_and_update_metadata(mongo_client, records):
	archived_employees = await mongo_client.fetch_employees_async(archived=True)

	to_be_deleted = [
		record
		for record in records
		# if record in archived_employees
	]

	async for record in to_be_deleted:
		await delete_record(record)
```

So how did I delete all records? You guessed right, I forgot to uncomment the line that made sure to only delete archived employees.

Why did I miss this? Well, for one, [async programming](https://docs.python.org/3/library/asyncio.html) in Python was new to me. So was [MongoDB](https://www.mongodb.com/docs/drivers/motor/). I had to keep a lot of concepts in mind. In addition, the code base was quite long and especially the `mongo_client` a blackbox.

Looking at [my post about confusion in programming]({{% ref "./confusion-is-part-of-programming.md" %}}), I was confused due to all 3 reasons mentioned, but mostly because of a  *lack of information*: My short-term memory (STM) ran out of slots, so it had to eject the commented line.

Since we only have 5 to 9 slots available, we need to find ways to support the STM. The most important tool to do so is code [chunking](https://en.wikipedia.org/wiki/Chunking_(psychology)): Grouping statements or lines in your code to ease reading and comprehending it.

There are ways to make chunking easier when writing the code as well:

1. Use [software design patterns](https://en.wikipedia.org/wiki/Software_design_pattern) because they allow for repeatable code.
2. Write comments to mark important parts of the code.
3. Leave beacons in your code: In addition to comments, beacons are signifiers in your code that make it easier to understand functionality. This can be the consistent naming of loop variables or idiomatic variable names (like `root` or `child` when using a tree-based datastructure):

```python
def execute(obj):
	if obj.lst:
		for x in obj.lst:
			execute(x)

# or with beacons
def traverse(node):
	if node.children:
		for child in node.children:
			traverse(child)
```

A lot easier to chunk with beacons, right? 🤓

If you use those or not, you still have to *practice chunking* if you want to support your STM. How could this practice look like?

1. Choose a code repository you are familiar with, for example your current project.
2. Select a class, function or method with less than 50 lines of code.
3. Study the code for 2 minutes.
4. Now recreate the code digitally or analog.
5. Compare and reflect! What was easy to recreate, was there something you could recreate partially, does the difficult to recreate code contain unknown concepts?

If you have coworkers, do this exercise together. Discuss your findings. Adapt how you write code and if you want to introduce beacons, comments or design patterns.

If your coworker is an LLM, think about how to include some of the techniques in your configuration. You are going to read a lot of generated code in that case, with a lot of complexity, and potentially a lot of unknown concepts. Repeat the exercise with your generated output if necessary to refine your approach.

So next time you notice a challenge in reading code, especially during a code review, think of your STM and how you can support it. ✌️

[^1]: Also at that time I had already handed in my resignation. Never let anyone who has resigned handle critical services. 🥸

+++
date = '2026-09-17T21:14:00+02:00'
draft = true
title = 'Deliberate Practice Beats Brain Rot'
+++

I have one major advantage over my colleagues who switched to agentic coding recently:

I already stopped coding professionaly over a year ago. 🥸

While I miss the good old days, I also like requirements engineering and the social aspects of being in pre-sales a lot. At the same time, I had to learn a lot of stuff unrelated to coding. Since [you can't have your cake and eat it](https://en.wikipedia.org/wiki/You_can%27t_have_your_cake_and_eat_it), I now have a lot less practice in coding.

As promised in [my last post]({{% ref "./confusion-is-part-of-programming.md" %}}), I want to talk about this practice (and the lack of it) today.

When you stop coding, a couple of things happen (roughly in that order):

1. You forget how to use your favourite library.[^1]
2. You forget how to use your favourite web framework.[^2]
3. You forget the last language feature added to your favourite programming language right before you stopped coding.[^3]

A similar process is to be expected when moving from organic coding to agentic coding. Why is that the case? This has to do with how our long-term memory (LTM) works.

Accessing information from your LTM is based on two strengths: *Storage strength* and *retrieval strength*. Storage strength grows the more you learn about a subject and can only grow over time[^4]. Retrieval strength on the other hand decays over time without proper training.

To understand how to train it, you must understand how information (e.g., about libraries, frameworks, or language syntax) are stored in the LTM. They are divided into two categories of *memories*:

1. Procedural memories, which you gathered *implicitly* and are responsible for motor skills. Muscle memory is a part of procedural memories.
2. Declarative memories, which you gathered *explicitly* and are knowledge and facts.

Declarative memories themselves are divided into *episodic memories* (like when you solved that one particular difficult bug[^5]) and *semantic memories* (like how to use [`pd.DataFrame.explode()`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.explode.html) properly).

Each type of memory requires different ways of training:

- *Procedural memories* are created through physical repetition. Remember when you learned how to touch type?
- *Episodic memories* form by going through three distinct phases:
	1. Starting with the *cognitive phase*, a learner has to break down information into subtasks and understand each on its own.
	2. Continuing with the *associative phase*, patterns emerge from those subtasks and make the information easier to grasp.
	3. Finally, in the *autonomous phase*, the learner has mastered the information and understands the information as a whole.

The easiest way to go through these phases is through *deliberate practice*. Remember school and learning new vocabulary with [flash cards](https://en.wikipedia.org/wiki/Flashcard)? That was deliberate practice! While you can of course learn programming language syntax or library function calls (which are semantic memories) through flash cards, episodic memories best form by working through problems, like implementing small variations of similar coding challenges or reading tons of source code.

When it comes to reading source code, different techniques can be used to support the LTM as well. This is something I am going to write about tomorrow. 🤓

[^1]: 🐼
[^2]: I miss coding with [Django](https://www.djangoproject.com).
[^3]: I still think Python doesn't need the [`match` statement](https://docs.python.org/3/tutorial/controlflow.html#match-statements).
[^4]: That is at least the scientific consensus as of 2021, when [The Programmer's Brain](https://www.manning.com/books/the-programmers-brain) was written.
[^5]: Or that one time you accidentally deleted the prod database with a stale backup 🥲.

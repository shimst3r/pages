+++
date = '2026-09-16T19:01:23+02:00'
draft = false
title = 'Confusion Is Part of Programming'
+++

I never had formal teacher training, yet somehow I always managed to become an educator or trainer next to my "official" work title.

Since 2016, I was a teaching assistant for higher mathematics, coach for test-driven development, initiator of a coding dojo for learning [Go](https://go.dev) (the language, not the board game), host of a book club reading [Google's SRE book](https://sre.google/sre-book/table-of-contents/), Scrum Master[^1], and organiser of a weekly office hour to explain AI products to my sales colleagues.

Or in short: Whenever a new challenge comes up that can be solved with enablement or training, I quickly find a way of supporting my colleagues.

After my current team introduced [agentic coding](https://arxiv.org/html/2508.11126v1), it became apparent to me that thinking about coding has to change. The sooner the better. So I started to think about what unique challenges agentic coding brings with it. To me, there are two properties that make it especially difficult:

1. The sheer amount of new code that needs to be reviewed[^2].
2. The speed at which existing coding skills deteriorate when not using them frequently[^3].

Today I want to shine a light on why reviewing code is difficult, but I plan a future blog post on maintaining coding skills through peer-assisted learning (my favourite learning technique). 

The first book I thought of while researching the topic was [The Programmer's Brain](https://www.manning.com/books/the-programmers-brain) by [Felienne Hermans](https://www.felienne.nl/over-mij/). The author is a professor for computer science education and uses the book to discuss insights from cognitive science relevant for software developers.

As she summarises:

> Confusion is part of programming. [...] It’s not a problem to be confused for a while, of course, but you don’t want to be confused for longer than needed.

With agentic coding, I feel most of my colleagues are confused most of the time. To a point where confusion gets replaced with apathy, which in turns leads to dissociation from their code being "their code". 

So why is it that programming leads to confusion? Hermans lists three reasons:

1. Confusion due to *Lack of knowledge*.
2. Confusion due to *Lack of information*.
3. Confusion due to *Lack of processing power*.

She associates these three types of confusion with parts of a simplified model of the cognitive processes that are in action while programming:

1. The long-term memory (LTM), which stores information like a hard drive, relates to a *lack of knowledge*.
2. The short-term memory (STM), which makes information available like the RAM or cache, relates to a *lack of information*.
3. The working memory, which acts like the CPU of the brain, relates to a *lack of processing power*.

During a code review, all three confusions can occur.

When reading code using a programming language, framework or code library that is new to you, you can't retrieve the required knowledge from your LTM. Instead, you have to look up the relevant documentation online or in your IDE, causing a disruption in your flow[^4], adding to your cognitive load.

While parsing a pull request, your STM temporarily stores keywords, variable names, data structures, and more. Your STM is very limited, with only a few slots available. How few? 7, plus/minus 2[^5]. The worse you are at chunking the program at hand, the more slots in your STM get used, the sooner you become confused due to a lack of information.

Finally, when tracing a program (trying to mentally execute the code in your head) to understand or debug it, you will quickly feel the urge to write something down, like the value of a variable or the contents of an array. Once you feel this urge, you are confused due to a lack of processing power.

With agentic coding, you will be confused sooner and more thoroughly.

: My hypothesis is, with agentic coding, you will be confused sooner and more thoroughly. Unless you practice deliberately to work through this confusion and have guardrails in place to support your LTM, STM, and working memory.

I identified both deliberate practice and guardrails based on cognitive science as the tools I want to utilise to support my team in dealing with AI code reviews. Stay tuned because I will write about a couple of ideas I have (motivated by The Programmer's Brain) in the next days. ✌️

[^1]: Debatably the only job I had that came close to a "certified educator".
[^2]: Assuming the team wants to maintain its high quality standards for agentic code.
[^3]: For example, see [[Maier et al. 2026]](https://arxiv.org/html/2605.04779v1).
[^4]: Often leading to checking your social feeds or worse. 🥸
[^5]: See [[Miller 1956]](https://psycnet.apa.org/doi/10.1037/h0043158).

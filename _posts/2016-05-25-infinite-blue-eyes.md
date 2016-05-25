---
layout:     post
title:      "Infinite Blue Eyes Puzzle"
subtitle:   "gotta get off this rock, Chuck"
date:       2016-03-28 21:18:00
header-img: "img/math-bg.png"
---

Okay, so, was asked by my friend and colleague
[Dr. Stephen "Danger" Ware][ware] on a Facebook post about another
[interesting puzzle concerning infinity][infinity puzzle] if the
[Blue Eyes Puzzle][blue eyes puzzle] could be extended to an infinite number
of islanders. Intuitively, it seems reasonable that the
[solution][blue eyes solution] should generalize nicely: if there are infintely
many pairs of blue eyes, it will still take "infinitely many days". But, these
things can be subtle once infinity is thrown into the mix,
so I thought it'd be fun to attempt a rigorous treatment
of the question.

[ware]: http://stephengware.com/
[infinity puzzle]: https://www.reddit.com/r/AskReddit/comments/4kz3di/whats_your_favourite_maths_fact/d3jj88j
[blue eyes puzzle]: http://xkcd.com/blue_eyes.html
[blue eyes solution]: https://xkcd.com/solution.html

First things first, I'm going to reformulate the puzzle which avoids the words
"everyone is a perfect logician", which for some reason bugs me more than
speaking of infinity or islanders who cannot communicate with each other.

So, suppose there is an island with several inhabitants. These islanders cannot
communicate with each other, but they share a few truths:

* All islanders know the color of every other islander's eyes, but not their own.
* If an islander can ever logically deduce the color of their own eyes, they
  will perish at noon on the following day.
* Any message washed ashore in a bottle can be trusted.

Now as it happens, at 12:01pm on Day 0, a message washes ashore in a bottle,
and is read by all the islanders:

> There is at least one islander with blue eyes.

What happens?

## Finite solution

Of course, since it wasn't specified, you would reasonably assume that there
are only finitely many islanders. But, in fact, the following solution works
for infinitely many islanders, as long as 

---
layout:     post
title:      "Infinite Blue Eyes Puzzle"
subtitle:   "like a deep blue sea"
date:       2016-05-26 10:18:00
header-img: "img/math-bg.png"
---

I was asked by my friend and colleague
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

First things first, I'm going to reformulate the puzzle to avoid the words
"everyone is a perfect logician", which for some reason bugs me more than
dealing with infinity or islanders who cannot communicate with each other.

So, suppose there is an island with several inhabitants. These islanders cannot
communicate with each other, but they share a few truths:

* All islanders are immortal, except as explained below.
* All islanders know the color of every other islander's eyes, but not their own.
* If an islander has enough information to logically deduce the color of their
  own eyes, they will perish at midnight of the following day, which will be
  noticed by the other islanders.
* Any message washed ashore in a bottle can be trusted.

Now as it happens, at 12:01am on Day 0, a message washes ashore in a bottle,
and is read by all the islanders:

> There is at least one islander with blue eyes.

What happens?

## Finite solution

Of course, since it wasn't specified, you would reasonably assume that there
are only finitely many islanders. But, in fact, the following solution works
for infinitely many islanders, as long as only finitely many have blue eyes.

The easy case is when there is only one islander with blue eyes. She reads
the message, looks around, and sees no one else with blue eyes. Therefore,
she correctly deduces she must be the islander with blue eyes. So, at midnight
on Day 1, she's dead as a doornail.

What about the rest of them? Well, suppose you are another islander. You
may be right to fear that you have blue eyes when that message arrives.
However, you saw at least one other person on the island who did have blue eyes,
which means that the message told you absolutely nothing new about yourself.
Importantly, you have no other way of gaining more information
*except by observing when other islanders perish or survive on following days*.
Thus, you will not die on Day 1.

Now, when you see the blue-eyed islander pass away at noon on Day 1, her
passing is itself new information. Putting yourself in her shoes, you realize
that if you had blue eyes, she'd have been in the same position as you were
the previous days, and would have lived just as you did. Alas, she did not,
so you conclude she saw that your eyes were not blue, and since they could
be any other color, you rest easy with the lack of knowledge. Thus you,
and every other islander, live on.

So, we have proven the following fact.

**Proposition** If there is only one islander with blue eyes, she will
perish at midnight on Day 1, and all others will survive.

However, we are more interested in the lemmas which led us to this
conclusion.

**Lemma 1'** If an islander sees at least one islander with blue eyes, she cannot
deduce her eye color by Day 1.

**Lemma 2'** If an islander sees no other islanders with blue eyes, she can
deduce her eye color by Day 1.

We'd like to prove two generalizations. We will always assume
\\(N\\in\\omega=\\{0,1,2,\\dots\\}\\).

**Lemma 1** If an islander sees at least \\(N\\) other islanders with blue
eyes, she knows on Day \\(0\\) that she will not be able to deduce her eye
color before Day \\(N\\).

*Proof.* This is trivially true for \\(N=0\\), so by induction we may assume
it is true for
\\(N\\) and aim to show it for \\(N+1\\). Let \\(Alice\\) be such
an islander who sees at least
\\(N+1\\) blue-eyed islanders. By induction, she cannot deduce her eye color
by noon on Day \\(N\\) as she sees at least \\(N\\) blue-eyed islanders.
Importantly, Alice realizes that no other islander can deduce their eye
color by then either! Any blue-eyed islander besides \\(Alice\\) can see
the other \\(N\\) blue-eyed islanders \\(Alice\\) observed, so they also are
subject to the induction hypothesis. And of course the non-blue-eyed islanders
can see the same \\(N+1\\) blue-eyed islanders \\(Alice\\) noticed, so they
too see at least \\(N\\) pairs of blue eyes.

Since \\(Alice\\) knows from Day \\(0\\) that no other islander can deduce his
own eye color during the first \\(N\\) days, so she gains no information she
cannot deduce herself from the beginning when noon on day \\(N\\) rolls around
and everyone is still alive. Therefore,
she still cannot deduce her eye color by noon on day \\(N+1\\). \\(\\square\\)

**Lemma 2** If an islander sees \\(N\\) other islanders with blue eyes who
are alive on Day \\(N\\), then she can deduce her eye color by Day \\(N+1\\).

*Proof.* We again proceed by induction as this holds for \\(N=0\\). Let
\\(Alice\\) be an islander who sees \\(N+1\\) other islanders with blue eyes
who are alive on Day \\(N+1\\). Let \\(Bob\\) be one of the islanders she
observes with blue eyes. She proceeds by contradiction. If she lacked blue
eyes, then on Day \\(N\\) Bob would have seen the \\(N\\) other islanders with
blue eyes that Alice observed. Thus, by induction, he would have perished
at midnight on Day \\(N+1\\), a contradiction. Therefore, Alice may deduce
that she has blue eyes. \\(\\square\\)

<small><i>
It's interesting that I used contradiction above. It would seem that Alice must
assume the <a href="https://en.wikipedia.org/wiki/Law_of_excluded_middle">
Law of the Excluded Middle</a> here, but I am not a logician, so perhaps
I missed something.
</i></small>

**Theorem 3** If there are \\(N+1\\) islanders with blue eyes, they will
perish at midnight on Day \\(N+1\\), and all others will survive.

*Proof.* Each blue-eyed islander sees \\(N\\) other islanders with blue
eyes, so by the above lemmas they will be alive on Day \\(N\\), but must
perish on Day \\(N+1\\). The other islanders see \\(N+1\\) other islanders
with blue eyes, and thus survive on Day \\(N+1\\). Since the blue-eyed islanders
perished that morning, the others deduce that they cannot have blue eyes,
but cannot specify their eye color further and thus survive.
\\(\\square\\)

## What's the wait for?

It's worth pointing out that when there is more than one islander with blue eyes,
no one gains information from the message on the bottle. So, what's the hold up?
It wasn't obvious to me from the above proof (even though I wrote it!),
so here's my intuition.

The important thing to note is that if you see \\(N+2\\) people with blue eyes,
you are waiting until they give you more information. You cannot tell if your
eyes are blue or not. And if they aren't, a blue-eyed islander sees only
\\(N+1\\) people with blue eyes. In their shoes, they have the same uncertainty,
and they should consider the possibility they lack blue eyes, in which case
the other blue-eyed islanders see only \\(N\\) people with blue eyes.
And so on, and so forth. The idea is that you know it will take at
least \\(N+1\\) days to remove the uncertainty from the other islanders with blue
eyes, because they lack information you have about their own eyes.
That's why the wait is required.

## The infinite case

So, we've handled the case where there are an arbitrary number of islanders
(even infinite!), but only finitely many islanders with blue eyes. So,
what if there are infinitely many islanders with blue eyes?

Well, we already have a very nice lemma above, **Lemma 1**. That allows us
to prove that, since all islanders see infinitely many pairs of blue eyes,
no islander can deduce their eye color by Day \\(N\\) for all
\\(N\\in\\{0,1,2,\\dots\\}\\).

So, assuming that our days are limited to the finite ordinals, the case is
closed. But why should we stop there? What if there exists a day for every
[ordinal number][ordinals]?

[ordinals]: https://en.wikipedia.org/wiki/Ordinal_number

We should consider what happens on Day \\(\\omega\\). Will anyone wake up dead?
The answer is of course, no. All islanders were able to deduce from the
beginning that no one could perish after a finite number of days, so
by the time Day \\(\\omega\\) begins, no one has gained information they didn't
already have. We shall be able to extend this argument by
[transfinite induction][transfinite induction] to handle every ordinal
(regardless of the cardinality of the ordinal or the set of blue-eyed islanders).

[transfinite induction]: https://en.wikipedia.org/wiki/Transfinite_induction

**Theorem 4** If there infinitely many islanders with blue eyes, then no islanders
can deduce their eye color by Day \\(\\alpha\\), where \\(\\alpha\\) is any ordinal.

*Proof.* If \\(\\alpha\\) is finite, we are done by Lemma 1. By transfinite induction,
we may assume the theorem holds for all \\(\\beta\\lt\\alpha\\). In order to
deduce her eye color by Day \\(\\alpha\\), \\(Alice\\) requires new information on
a previous day. However, by the induction hypothesis, \\(Alice\\) knows from
the beginning that every islander cannot deduce their eye color by a previous
day. So, if \\(\\alpha\\) is a limit ordinal, we are done. The other case
is when \\(\\alpha=\\beta+1\\) for some \\(\\beta\\lt\\alpha\\). Alice wakes up
on Day \\(\\beta\\), and is immediately bored. She already knew that everyone
sees infinitely many islanders with blue eyes, so she already knew that
everyone would be alive. Indeed, they are. So, she has gained no new information
that morning, and therefore cannot deduce anything new by the end of the day,
the beginning of Day \\(\\alpha\\). \\(\\square\\)

## In conclusion

In working on this article, I was particularly amused by the following:

* If the cardinality \\(\\kappa\\) of islanders with blue eyes is **finite**,
  then all blue-eyed islanders will **perish** after finitely-many days.
  (Specifically, \\(\\kappa\\)-many.)
* If the cardinality \\(\\kappa\\) of islanders with blue eyes is **infinite**,
  then all blue-eyed islanders will **remain alive** no matter how many days
  pass, even after \\(\\kappa\\)-many days.

I have some intuition here: in any case, the unknown datum for each
islander (their own eye color) is finite. Thus, if there are finitely many
blue-eyed islanders, this datum is important! But, if there are infinitely many
blue-eyed islanders, then the status of an islander's own eyes is irrelevant
to the cardinality of that set. Therefore, the bottled message, which says
that the cardinality of blue-eyed islanders is positive, gives no new information
to the islanders, **because they already have exactly the same information about
the cardinality of blue-eyed islanders**.

I hope you found all that interesting. If you have any comments or questions,
shoot them to me at [@StevenXClontz](http://twitter.com/StevenXClontz).
Thanks for reading! :-)

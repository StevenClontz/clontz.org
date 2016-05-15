---
layout: page
title: "Puzzle Types"
description: "math, word, logic, and more"
header-img: "img/puzzles-bg.jpg"
permalink: /puzzles/types/
---


Generally speaking, a [puzzle](/puzzles/)
is any question/problem which satisfies two properties:

* It is designed to entertain the solver.
* There is a well-defined solution.

This can be accomplished through many methods, so I'd like to attempt to categorize
many of these variants.

Note that Wikipedia attempts to do so as well, so feel free to just
visit <https://en.wikipedia.org/wiki/Puzzle> if you like your puzzle categorization
crowd-sourced (who doesn't?).

## Mechanical Puzzles

Examples include jigsaw puzzles, nail puzzles, Rubik's Cubes.

Probably the most common variant of puzzle; I expect most puzzlers consider a
jigsaw piece as the "logo" for puzzling. Not much else to say here.

## Logic Puzzles

Examples include [Sudoku](https://en.wikipedia.org/wiki/Sudoku),
[Picross](https://en.wikipedia.org/wiki/Nonogram),
[logic grid puzzles](https://en.wikipedia.org/wiki/Logic_puzzle#Logic_grid_puzzles).

A logic puzzle is typically characterized by a grid which must be completed by
following some well-defined rules. Generally such puzzles have a unique solution
(a property which itself helps the solver filling the grid). Often these
puzzles may be made easier by partially filling out the puzzle for the solver.
I'm a particular fan of picross puzzles (also called nonograms) because the solution
paints a picture (i.e. gives the solver new information unrelated to the properties
of the puzzle itself).

## Math puzzle

Example:

> Suppose `xy=6`, `xz=10`, and `yz=15`. What is `xyz` equal to?

What distingishes these from other types of math *problems* in that a math
puzzle is meant to be recreational, or
perhaps competitive. These puzzles typically don't lend themselves to algorithmic
solutions; at least, not algorithms which are traditionally taught in school, anyway.
See also: AMC comeptitions, Putnam problems, pretty much any math competition
you can think of. (Almost...)

By the way, the trick in the example is to not try to solve for `xyz`, but first try
to solve for `x^2y^2z^2`... It's a fun puzzle the first time you hear it, but the
top competitors in these competitions memorize hundreds of tricks just like that.

## Cryptic puzzles

Kind of hard to give examples of these, because they are generally "designer" puzzles
which are meant to be solved at most once by a given person, perhaps in the context
of a puzzlehunt competition. In a cryptic puzzle, the goal/answer is still
well-defined (i.e. enter the an 8-digit number into an online form which is
accepted; find a clue to a location where a previously designated token can be found).
However, the mechanics of decyphering this solution are left completely vague,
and it's up to the solver to guess at several interpretations of what the puzzle
could mean until one fits.

These are probably the hardest to design, because there's no "correct" way for a player
to approach such a puzzle. I could go into more detail, but that's a whole book of
material on its own. (If you want to pay me an advance, however...)

## Word puzzles

Examples include crosswords, Boggle.

Word puzzles are puzzles which require knowledge of a language. Most word puzzles are
actually mathematical in nature assuming a dictionary is available; for example,
there are 120 ways to permute the letters in a five-letter word without repeated letters,
and there are 104 possible three-letter words in a 4 by 4 grid of letters.

The line gets blurred a bit with crossword puzzles; technically (as was pointed out
by fellow puzzler Christopher Night) crosswords may have multiple answers and are
up to interpretation (like pattern puzzles). In general, word puzzles which are based
on defintions have a bit of flexibility (unless there's a way to check the solution),
so designing them takes finesse.

## Trivia puzzles

Similar to cryptic puzzles, trivia puzzles usually have custom designs (otherwise,
they're just plain trivia). While trivia puzzles often have cryptic elements, they
may also be explicit. What they do require is either knowledge of some sort of
trivia, or access to the internet. As such, they may also be called research
puzzles when internet access is allowed or encouraged.

## Mathematical puzzles

Wait, didn't I already go over these? So, this is personal preference,
but I actually distinguish math puzzles from mathematical puzzles.
Here's how I separate the two:

* A math puzzle is a math problem.
* A mathematical puzzle is a puzzle which uses/encourages mathematics.

For example (and yeah, this is a classic):

> 100 people are in a room, and everyone high-fives one another. How
> many high-fives total occurred?

You may rightfully say that this is just a word-based math puzzle,
but the distinction I draw is that players are given the freedom
to model the above question however they wish. There's always
the brute force solution:

```
99+98+...+2+1=4950
```

But you could also approach this problem by expressing it as a
graph ("how many edges are in the complete graph with 100
vertices?"), or making the clever observation that each person
performs 99 high fives, so divide that number by two:

```
100*99/2=4950
```

These puzzles have the advantage of being educational, without
the appearance of being a math problem.

---

A couple related concepts:

## Riddles

Example:

> A man and his son are involved in a car accident. The father dies, but the son
> is taken to the hospital. The doctor refuses to operate, saying "I cannot
> operate on my son!" How can this be?

Riddles don't fit my definition of a puzzle, but they might fit yours,
so here you go. Note that there are a few answers to the above riddle:
"The doctor is the mother!" "The doctor is the step-father!" "The doctor is
the adopted father!" etc. etc.

## Pattern puzzles

Example:

> What comes next in the list? 1, 2, 4, ...

Another non-puzzle example. Especially egregious are
"which picture comes next in the pattern" Mensa-type questions. Since
I'm a mathematician, I'll point out that in the example,
both `f(n)=2^n` and `g(n)=(1-n)(2-n)/2+2n(2-n)+4n(n-1)/2`
satisify `f(0)=g(0)=1`, `f(1)=g(1)=2`, and `f(2)=g(2)=4`, but
`f(3)=8` and `g(3)=7`. Of course, you may prefer `f` because it's simpler,
and you may have a point.

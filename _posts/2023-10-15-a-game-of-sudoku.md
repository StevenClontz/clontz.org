---
layout: post
title: "A Game of Sudoku"
subtitle: "a few theorems"
header-img: "img/math-bg.png"
date: 2023-10-15 16:00:00
---

Almost a decade ago I first thought about the following game.

---

### Definition

The game **Sudoku VS** proceeds as follows for two players.
The game begins with an empty Sudoku grid. Players alternate
filling digits into the grid, as long as the usual Sudoku
constraints are satisfied (no repeats in each row, column,
and 3x3 box). Note that a move that results in an impossible
Sudoku puzzle (e.g. a square that's impossible to fill)
is allowed. The first player to be unable to fill a digit
loses.

---

As a finite two-player game of perfect information, a standard
result of game theory guarantees that one player has a
**winning strategy**, a strategy that results in victory no
matter how the opposing player moves.

And that's as far as I really got with it, setting the problem
aside until a few weeks ago when I suggested it offhand to
my student Daniel Hodgins. Daniel found it interesting enough
to make it the topic of
[Gordon Hamilton](2023-10-14-ams-sectional-session-notes.md)'s
weekly Problem Incubator. Spending a couple of hours, we
came up with the following results.

---

### Definition

The game **LSVS(n)** ("Latin Square VS") proceeds as follows
for two players. The game begins with an empty $n\times n$ grid.
Players alternate
filling digits into the grid, as long as the usual Latin square
constraints are satisfied (no repeats in each row and column)
The first player to be unable to fill a digit
loses.

---

### Proposition

The first player wins every playthrough of LSVS(1), and the
second player wins every playthrough of LSVS(0) and LSVS(2).

#### Proof

We show the result for LSVS(2). Player 1 first plays in
some cell. Player 2 may then play the opposite number in
the opposite corner. This results in no remaining legal plays
(where `.` denotes an empty cell, and
 `x` denotes an empty cell that can no longer be filled).

```
.. -> .2 -> x2
..    ..    1x
```

This describes an elegant winning strategy, however, the theorem
asserts that Player 2 wins *no matter how they play*. So we enumerate
the remaining two possibilities (up to symmetry).

Suppose instead Player 2 played the same digit in the opposite
corner. Then there are only two remaining legal moves, and
no matter which Player 1 picks, the other remains available for
Player 2.

```
.. -> .2 -> .2 -> 12 -> 12
..    ..    2.    2.    21
```

Finally, Player 2 might play in an adjacent corner.
As before, there are only two remaining legal moves, and
no matter which Player 1 picks, the other remains available for
Player 2.

```
.. -> .2 -> .2 -> 12 -> 12
..    ..    .1    .1    21
```

---

This suggests a wild conjecture: perhaps Player N wins every
playthrough of LSVS(M) if and only if $N\equiv M\mod 2$? However,
Daniel found the following scenario for a $4\times 4$ grid
which could go either way.

```
132x
3214
..4.
..x3
```



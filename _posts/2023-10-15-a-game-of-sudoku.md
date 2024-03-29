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
for two players. The game begins with an empty \\(n\times n\\) grid.
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
playthrough of LSVS(M) if and only if \\(N\equiv M\mod 2\\)? However, consider
the following maximal Latin squares:

```
1234
3x41
41x2
231x
```

```
1234
2341
3412
4123
```

Player 1 wins the first result, while Player 2 wins
the second.

Nonetheless, we were able to succeed in proving the following.

---

### Theorem

Player 1 wins every playthrough of LSVS(3).

#### Proof

The way we see this is by showing that there do
not exist partially-filled Latin \\(3\times 3\\)
squares using even-many cells that cannot be filled
further.
This is immediate when considering squares with only
\\(0\\) or \\(2\\) cells filled.

When considering \\(8\\) cells, we may assume (by
swapping rows/cols) that the lower-right cell
is unfilled, and the top row is `123`.

```
123
???
??.
```

There are only two legal ways to complete the second
row, which then each determine the bottom row. We
see by inspection that the missing cell can be filled.

```
123    123
231 or 312
31.    23.
```

For \\(4\\) cells, note that if a row is completely unfilled,
each cell of that row can be legally filled. So we need only
consider the situation where a diagonal (modulo swaps) is
filled. In the illustration below, the upper-right cell
is fillable.

```
?..
??.
..?
```

Finally, for \\(6\\) cells, we observe that there are only
three patterns to consider modulo swaps:

```
???    ???    ???
??? or ??. or ??.
...    ?..    ..?
```

In the first two patterns, it's clear that the lower-right
cell is fillable. To see the last, assume the top is `123`
and consider that in order to make the right cell unfillable,
there must be a fillable cell on the bottom row:

```
123    123
21x or 23x
..?    ..2
```

---

This was about as far as we got in the Incubator.
However, being newly excited about the problem, I
started pitching it around a bit. And with the AMS
Southeastern Sectional meeting hosted at my university
last weekend, I had the perfect audience.

Kudos to [Matt Noble](https://www.mga.edu/directory/people.php?name=noble-matthew)
for sharing the following very slick proof.

---

### Theorem

Player \\(N\\) has a winning strategy for LSVS(M)
if and only if \\(N\equiv M\mod 2\\).

#### Proof

Enumerate the cells of the \\(M\times M\\) grid by
\\(\{(i,j):0\leq i,j \lt M\}\\). Note that to define
a winning strategy, we need only define a legal move
for the winning player in response to any move of the opponent.

##### Odd case

In the odd case, Player 1 begins by playing \\(M\\) in the center
cell, which is of course legal.

Then whenever Player 2 plays \\(M\\) in the cell
\\((i,j)\\), Player 1 responds by playing \\(M\\) in the
cell \\((M-i-1,M-j-1)\\). Note that \\(M\\) cannot already
be in column \\(M-i-1\\) or row \\(M-j-1\\): if it was played
by Player 1, it was in resopnse to another play of \\(M\\)
by Player 2 in column \\(i\\) or row \\(j\\), making the move
\\(M\\) in \\((i,j)\\) illegal. And if it was played by Player 2,
Player 1 previously responded by playing in column
\\(M-(M-i-1)-1=i\\) or row \\(M-(M-j-1)-1=j\\), making the move
\\(M\\) in \\((i,j)\\) illegal.

Finally, whenever Player 2 plays
\\(m\lt M\\) in the cell \\((i,j)\\), Player 1 responds
by playing \\(M-m\\) in the cell \\((M-i-1,M-j-1)\\). The legality
of this move can be proven similarly to the prior argument, noting
\\(M-(M-m)=m\\).

##### Even case

In the even case, whenever Player 1 plays \\(m\\) in the cell
\\((i,j)\\), Player 1 responds by playing \\(M-m+1\\) in the
cell \\((M-i-1,M-j-1)\\). The legality
of this move can be proven similarly to the prior arguments, noting
\\(M-(M-m+1)+1=m\\). and \\(M-m+1\not=m\\)

---

Note that the above strategy for Player 1 in the odd case
is also a winning strategy for Player 1 in Sudoku VS, by similar
symmetry arguments.

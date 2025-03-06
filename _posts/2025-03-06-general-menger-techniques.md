---
layout: post
title: Illustrating versitile selection game techniques
subtitle: generic conditions for obtaining results
header-img: "img/math-bg.png"
date: 2025-03-06 14:15:00
---

Today Davide gave a
[very interesting talk](https://preview.scholarlattice.org/events/35ad79fe-ae43-4638-ac60-863bda4c712d)
in the 2025 Spring Topology and Dynamics Conference on
[[Aurichi, Bonanzinga, and Giacopello 2024](https://www.sciencedirect.com/science/article/pii/S0166864124001214)].
Since it reminds me of some pretty versitile techniques I've
developed for analyzing selection principles/games in
[[C 2019](https://www.sciencedirect.com/science/article/pii/S0166864119300847)]
and
[[C 2020](https://www.sciencedirect.com/science/article/pii/S0166864120300031)], and I'm able
to answer a question the paper asks, I thought I'd write up
how to apply these general techniques for this specific topic.

The reader is expected to be familiar with the basic theory of
[selection games and principles](https://en.wikipedia.org/wiki/Selection_principle).

First, we recall the following.

---

### Definition

For a set $X$, let
$\mathbf C(X)=\{f\in(\bigcup X)^X:x\in X\Rightarrow f(x)\in x\}$
be the collection of all choice functions on $X$.

### Definition

The set $\mathcal R$ is said to be a **reflection**
of the set $\mathcal A$ if 
$$\mathcal A'=\{\operatorname{range} f:f\in\mathbf C(\mathcal R)\}$$
is coinitial in $\mathcal A$ with respect to $\subseteq$;
that is, $\mathcal A'\subseteq \mathcal A$, and for all
$A\in \mathcal A$, there exists $A'\in \mathcal A'$ such that 
$A'\subseteq A$.

### Definition

Two games are said to be **dual** if a winning strategy for
Player 1 (resp. 2) in either game using a certain amount
of information can be used to define a
winning strategy for Player 2 (resp. 1) in the other game
using corresponding information.

*Note.* I'll point the reader to definitions 16-19 of
[[C 2020](https://www.sciencedirect.com/science/article/pii/S0166864120300031#en0170)]
to more carefully explain what "certain amount"
and "corresponding information" mean here.

### Theorem 1 (Corollary 26 of [[C 2020](https://www.sciencedirect.com/science/article/pii/S0166864120300031#en0330)])

If $\mathcal R$ is a reflection of $\mathcal A$, then
$G_1(\mathcal A,\mathcal B)$ and
$G_1(\mathcal R,\neg\mathcal B)$ are dual.

(Here, $\neg\mathcal B$
is the complement of $\mathcal B$ in the appropriate set, that is,
**Player 1** rather than Player 2 wins
if the game produces an element of $\mathcal B$.)

---

This provides us the machinery necessary for the following.

---

### Definition

Let $\mathscr N$ denote the collection of 
[networks](https://en.wikipedia.org/wiki/Base_(topology)#Weight_and_character)
of a topological space.

### Definition

Let $\mathcal P_x(U)=\{S\subseteq U:x\in S\}$
and
$\mathcal R=\{\mathcal P_x(U):x\in X,U\text{ is an open neighborhood of } x\}$.

### Theorem 2

$G_1(\mathscr N,\mathscr N)$ and
$G_1(\mathcal R,\neg\mathscr N)$ are dual.

#### Proof

By Theorem 1, we need only show $\mathcal R$ is a reflection
of $\mathscr N$. Let 
$$\mathscr N'=\{\operatorname{range} f:f\in\mathbf C(\mathcal R)\}$$

We must first confirm $\mathscr N'\subseteq\mathscr N$, that is,
each $\operatorname{range} f$ is a network. To see this, let $U$
be an open neighborhood of $x$, and consider $f(\mathcal P_x(U))\in\mathcal P_x(U)$; it follows $x\in f(\mathcal P_x(U))\subseteq U$. Since $f(\mathcal P_x(U))\in\operatorname{range} f$, we're done.

We now confirm that $\mathscr N'$ is coinitial in $\mathscr N$. So let
$\mathcal N\in\mathscr N$ be a network. Then for each $x\in X$ and
open neighborhood $U$ of $x$, we may choose
$f(\mathcal P_x(U))\in\mathcal N$ such that $x\in f(\mathcal P_x(U))\subseteq U$. Then $f\in\mathbf C(\mathcal R)$ and thus $\operatorname{range} f\in\mathscr N'$. Finally, note
$\operatorname{range} f\subseteq\mathcal N$.

### Corollary

The R-nw-selective game and PO-Set games of
[[ABG 2024](https://www.sciencedirect.com/science/article/pii/S0166864124001214)]
are dual.
(This is Proposition 2.4 of ABG 2024 and answers its Question 2.5.)

#### Proof

As defined in
[[ABG 2024](https://www.sciencedirect.com/science/article/pii/S0166864124001214)]
the PO-set game is exactly
$G_1(\mathcal R,\neg\mathscr N)$: Player 1 chooses a point and open
neighborhood, then Player 2 chooses some subset of that neighborhood
containing the point; Player 1 wins provided the choices of Player 2
form a network.

ABG 2024 defines the R-nw-selective game to be
$G_1(\mathscr N_\omega,\mathscr N_\omega)$ where $\mathscr N_\omega$
collects the *countable* networks of the space.
However, it's immediate that any collection chosen
by Player 2 will be countable, so $G_1(\mathscr N,\mathscr N)$
and $G_1(\mathscr N,\mathscr N_\omega)$ are equivalent games.

Now compare $G_1(\mathscr N,\mathscr N_\omega)$
and $G_1(\mathscr N_\omega,\mathscr N_\omega)$. First, any winning strategy
for Player 2 in $G_1(\mathscr N,\mathscr N_\omega)$ is a winning strategy
for Player 2 in $G_1(\mathscr N_\omega,\mathscr N_\omega)$.
But given a strategy for
Player 2 in $G_1(\mathscr N_\omega,\mathscr N_\omega)$... TODO

---
kind: article
title: 'Compact spaces with G_\delta diagonals are metrizable'
created_at: 2014-02-09 17:13
---

Too many web development posts! Time for some topology!

As an exercise I've worked through the classical result that if a space $$X$$
is compact Hausdorff and has a $$G_\delta$$-diagonal $$\Delta$$, then $$X$$ is 
metrizable. 
It relies on Urysohn's theorem that regular second-countable spaces are 
metrizable, and since compact Hausdorff spaces are normal*, I'll just show 
that the space is second countable.

When I went to compare, most of proofs I found online and in texts like 
Engleking were a lot less direct (involving characterizations
of $$G_\delta$$ diagonals using covers), so I hope someone gets 
some use out of this fairly straight-forward attack (due to a hint from 
my advisor Gary Gruenhage).

<!-- more -->

### Definitions

We'll assume you're good on most of the terms, but $$G_\delta$$ sets are 
countable intersections (from the $$\delta$$) of open sets (from the $$G$$). The
diagonal of a space is what you expect: 

$$\Delta = \{\langle x,x \rangle : x \in X \} \subseteq X^2$$

### Proof

Start by assuming that $$\Delta = \bigcap_{n<\omega} G_n$$ where 
$$G_{n+1} \subseteq G_n$$. Since $$X^2$$ is normal (not because $$X$$ is, but 
because $$X^2$$ is also compact Hausdorff) and $$\Delta$$ is closed, we can set
$$U_0=G_0$$, and
$$\Delta \subseteq U_{n+1} \subseteq \overline{U_{n+1}}\subseteq U_n \cap G_{n+1}$$.

It follows that 
$$\Delta \subseteq \bigcap_{n<\omega} U_n \subseteq \bigcap_{n<\omega} \overline{U_n} \subseteq \bigcap_{n<\omega} G_n = \Delta$$

These $$U_n$$ have a special property: for every $$x\in X$$ and every open 
neighborhood $$A$$ of $$x$$, there is some $$n<\omega$$ such that 

$$U_n[x]=\{y:\langle x,y\rangle \in U_n\}\subseteq A$$

To see this, suppose not: then we may choose $$x_n \in U_n[x]\setminus A$$. 
Since $$x_n \in \overline{U_m[x]}$$ for $$n\geq m$$, it follows that $$x_n$$ must 
converge in $$\bigcap_{m<\omega} \overline{U_m[x]} = \{x\}$$. But since $$x_n$$ 
converges to $$x$$, its neighborhood $$A$$ must contain all but finitely many 
$$x_n$$, a contradiction.

Now, since $$U_n$$ is open, we can choose open $$B_{x,n}$$ for each $$x\in X$$ such 
that  $$(B_{x,n})^2\subseteq U_n$$. Since $$X$$ is compact, let $$\mathcal{B}_n$$ 
be a finite subcover for $$\{B_{x,n}: x\in X\}$$ for each $$n<\omega$$.

We note that $$\mathcal{B} = \bigcup_{n<\omega} \mathcal{B}_n$$ is countable, 
and we claim it is a base for $$X$$. Let $$A$$ be a neighborhood of $$x$$; then 
choose $$U_n$$ such that $$U_n[x]\subseteq A$$. We need only take $$B_{z,n}$$ from 
the cover $$\mathcal{B}_n$$ of $$X$$ such that $$x\in B_{z,n}$$, and note that 
$$(B_{z,n})^2\subseteq U_n$$ implies $$x\in B_{z,n}\subseteq U_n[x] \subseteq A$$.
$$\Box$$


<small>
  *Not too bad: you can easily show that in Hausdorff spaces, not just 
  points can be separated by open sets, but all compact sets can be 
  separated by open sets. All closed subsets of compact spaces are compact, 
  so that's that.
</small>
---
layout: post
title: "Connectedness of finite topological spaces"
subtitle: "notes for combinatrorics seminar"
header-img: "img/math-bg.png"
date: 2024-03-18 09:15:00
---

Here's some rough notes on what I'll talk about at the
South Alabama combinatorics seminar on March 21.

- Motivation:
    - <https://math.stackexchange.com/questions/4812062>
    - <https://math.stackexchange.com/questions/4814029>
- Modeling finite topological spaces
    - Set + topology.
        - Ex: X=5, T=\{\{0,1\},\{1\},\{2,3,4\},\{3,4\}\}
    - Specialization preorder.
        - Ex: 0 ≺ 1, 2 ≺ 3, 2 ≺ 4, 3 ≺ 4 ≺ 3
    - Directed graph
    - [Connected](https://topology.pi-base.org/properties/P36/) 
      topology = connected of graph
- Biconnected ([π-Base P44](https://topology.pi-base.org/properties/P44/))
    - Connected space such that given two disjoint connected subspaces, 
      one is a singleton.
    - Equivalently, for any partition of the space into two connected
      subspaces, one is a singleton.
- Totally disconnected ([π-Base P47](https://topology.pi-base.org/properties/P47/))
    - Every subspace with more than one point is disconnected
- Has a dispersion point ([π-Base P47](https://topology.pi-base.org/properties/P47/))
    - Connected space with a dispersion point, a point whose removal
      results in a totally disconnected space
    - Ex: 0 ≺ 1,2,3,4 has 0 as a dispersion point
    - It's also biconnected: actually any space with a dispersion point
      is biconnected
- Question: among finite spaces, are biconnected spaces just the
  spaces with a dispersion point?
    - Not quite: 0, 0 ≺ 1, and 0 ≺ 1 ≺ 2 are biconnected without
      dispersion points
    - So we need an extra requirement, one that we hadn't ever thought
      to track in the π-Base...
- Thm: For finite spaces with at least 4 points, biconnected is equivalent
  to having a dispersion point.




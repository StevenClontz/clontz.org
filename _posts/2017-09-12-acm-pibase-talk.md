---
layout:     post
title:      "pi-Base: A usable map of the forest"
subtitle:   "Talk notes for South's ACM & Math Clubs"
date:       2017-09-12 10:16:00
---

Here are my notes for today's talk on [pi-Base][pi-base] for
the University of South Alabama's ACM and Math Clubs.

## Clontz.org

- Notes/links from this talk are available on my [website](http://clontz.org).

## Relationship of Math and Comp Sci

- Math folks: knowing computer science/engineering can help you get a job.
    - Don't have to take classes; just pick up a fun sideproject!
- CS folks: knowing math can help you get a job.
    - Having a math background makes people think you're (a) smart,
      (b) a problem-solver (in general).
- I hope to see future collaborations between ACM and Math Club, and I
  encourage members of both groups to be involved with the other and
  leadership to work together to support their memberships.

## What is Topology?

- Topology is the a of mathematical structure that generalizes geometry
  and calculus.
    - Classic example: [donut and coffee cup][donut]
    - My favorite example: [topology of fonts][font-puzzle]
    - Big data application: [persistent homology][ph]
- One goal of topology is to identify the properties of topological spaces
  that characterize them.
    - Compactness: \\([0,1]\\) is compact, but
      \\(\mathbb{R}\\) is not.
    - Hausdorff: \\([0,1]\\) is Hausdorff, but an indiscrete space is not.
    - Normal: \\([0,1]\\) must be normal, because it is compact & Hausdorff.

## What is pi-Base?

- Topologists have studied thousands of topological spaces and thousands of
  topological properties over the past century.
    - [Counterexamples in Topology][counterexamples] surveyed about 160 of
      these spaces and about 60 of these properties in 1970.
    - Paraphrasing the famous topologist Mary Ellen Rudin in her
      review of Counterexamples,
      [topology is a dense forest of counterexamples, and a usable map of the forest is a fine thing][rudin-quote].
    - [pi-Base][pi-base] began as a sideproject of my colleague
      [James Dabbs][dabbs] to digitize this information into a user-friendly
      web app.
    - Later pi-Base was opened up to community contributions.
- Features:
    - [Properties][properties]
    - [Spaces][spaces]
    - [Theorems][theorems]
    - Canonical naming as in [OEIS][oeis].

## Where is pi-Base going?

- Currently I have a small grant to convert pi-Base into a modern tool for
  mathematical researchers.
    - Major flaw in current version: lack of citations and peer-review.
    - ACM officer Cody Martin worked for me last summer to add citations
      from pi-Base to Counterexamples.
    - Once this audit is complete, all contributions will require references
      to a peer-reviewed manuscript to be marked as verified.
- pi-Base will become a treasure trove for undergraduate research.
    - There are still many unknowns in topology.
    - pi-Base can automatically catalog space/property pairs that are missing.
    - Three possibilities:
        - The question has been answered in literature not in pi-Base.
        - The question hasn't been answered because it's hard.
        - The question hasn't been answered because no one's tried: perfect
          for undergrads!

[pi-base]: http://pi-base.org
[donut]: https://en.wikipedia.org/wiki/Topology#/media/File:Mug_and_Torus_morph.gif
[ph]: https://www.math.upenn.edu/~ghrist/preprints/barcodes.pdf
[font-puzzle]: http://mappmath.org/puzzles/
[counterexamples]: https://en.wikipedia.org/wiki/Counterexamples_in_Topology
[dabbs]: http://jdabbs.com/
[properties]: https://topology.jdabbs.com/properties/P000013
[spaces]: https://topology.jdabbs.com/spaces/S000026
[theorems]: https://topology.jdabbs.com/spaces/S000026/properties/P000013
[rudin-quote]: http://www.jstor.org/stable/2318037?origin=crossref&seq=2#page_scan_tab_contents
[oeis]: http://oeis.org/A000045

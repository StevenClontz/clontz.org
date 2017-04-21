---
layout:     post
title:      "Alternate Standard Deviation Formula"
subtitle:   "the things you learn teaching MA 110"
date:       2017-04-21 11:52:00
---

While teaching MA 110 (Finite Mathematics), I casually introduced
standard deviation using the formula provided by our textbook,
where \\(\sum x\\) represents the sum of a dataset and
\\(\overline{x}=\frac{\sum x}{n}\\) is its mean:

\\[
  s
    =
  \sqrt{
    \frac{
      \sum (x^2) - n(\overline{x})^2
    }{
      n-1
    }
  }
\\]

But, this isn't my favorite formula for standard deviation, because it's
not really clear what it's trying to measure from its formula. The formula
I was more accustomed to makes it clear that standard deviation measures
the differences between datapoints and the mean, and then sums up the
squares of those differences. That is to say, it gives a measure of how
different the datapoints are from the average.

\\[
  s
    =
  \sqrt{
    \frac{
      \sum (x-\overline{x})^2
    }{
      n-1
    }
  }
\\]

But while the textbook uses that first formula, some of our online homework
uses the second formula when working out example solutions. So, for the
record, here is a proof that both formulas do in fact measure the same thing.

Note that we need only prove that the numerators of each fraction are equal.
So...

\\[
  \sum (x-\overline{x})^2
\\]

Applying \\((a-b)^2=a^2-2ab+b^2\\), we get:

\\[
  = \sum (x^2-2x\overline{x}+(\overline{x})^2)
\\]

We're allowed to add up each term separately.

\\[
  = \sum (x^2)-2\sum (x\overline{x})+\sum((\overline{x})^2)
\\]

Now, since the last term is just adding the same number
\\((\overline{x})^2\\) once for each of the \\(n\\) members of the dataset,
we may simplify it as follows.

\\[
  = \sum (x^2)-2\sum (x\overline{x})+n(\overline{x})^2
\\]

We may also factor out the constant \\(\overline{x}\\) from the middle sum.

\\[
  = \sum (x^2)-2\overline{x}\sum x+n(\overline{x})^2
\\]

It follows from \\(\overline{x}=\frac{\sum x}{n}\\) that
\\(n\overline{x}=\sum x\\), giving the following.

\\[
  = \sum (x^2)-2\overline{x}(n\overline{x})+n(\overline{x})^2
\\]

The solution is revealed by rearranging and combining like terms.

\\[
  = \sum (x^2)-2n(\overline{x})^2+n(\overline{x})^2
\\]

\\[
  = \sum (x^2)-n(\overline{x})^2 \hspace{1em}\Box
\\]

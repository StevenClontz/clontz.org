---
kind: article
title: "Complex exponents"

created_at: 2013-12-28 01:15

---

As usual, since I spent some time writing this up on [/r/learnmath](http://www.reddit.com/r/learnmath/), I'd like to share it with you guys. The OP asks:

> what does it mean to raise a number to the power of i?

I explain in [this comment](http://www.reddit.com/r/learnmath/comments/1tuq9y/what_does_it_mean_to_raise_a_number_to_the_power/cebqmng), but here it is too.

<!-- more -->

Alright, so, we're talking about complex numbers, so I'm assuming you know how to plot them in the complex plane and do basic addition/multiplication.

If we want to know what a number like $2^3$ means, it's pretty easy: you take $2×2×2=8$. Same for $(-3i)^3$ [(Wolfram Alpha)](http://www.wolframalpha.com/input/?i=%28-3i%29%5E3): it's $-3i\times -3i\times -3i=-27i$.

Think about what's happening visually: $2^3$ stretches the vector from the origin which used to point to $2+0i$, but now it points to $8+0i$. The effect on $(-3i)^3$ is more complicated: there's stretching, *and* reflection across the origin.

When you mix the two together, say, $(2-3i)^3$ [(Wolfram Alpha)](http://www.wolframalpha.com/input/?i=%282-3i%29%5E3) which is equal to $-46-9i$, you get stretching, and a reflection across the imaginary axis.

So, here's where the usefulness of raising a number to an imaginary (or complex) number kicks in: it gets us arbitrary rotations. It just so happens that multiplying a complex number by $e^{\theta i}$ rotates that number $\theta$ radians counter-clockwise around the origin. For example, $3e^{\frac{\pi}{2}i}$ [(Wolfram Alpha)](http://www.wolframalpha.com/input/?i=3e%5E%7B%5Cpi%2F2+i%7D) is $3i$ since that represents a rotation of $\frac{\pi}{2}$ or $90$ degrees.

You can take any complex number of the form $(a+bi)^i$ and manipulate it to be in the form $(c+di)e^{\theta i}$ (although that's out of the scope of this post). For example: $(1+i)^i$ [(Wolfram Alpha)](http://www.wolframalpha.com/input/?i=%281%2Bi%29%5Ei) can be manipulated to become $e^{\frac{\pi}{4}}2^{\frac{1}{2}i}$, which can be rewritten as $e^{\frac{\pi}{4}}e^{\ln(\sqrt{2})i}$ . So we're taking the point $e^{\frac{\pi}{4}}+0i$, and rotating it $\ln(\sqrt{2})$ (about $0.34$ or $\frac{\pi}{9}$) radians around the origin.

Since $(a+bi)^{c+di} = (a+bi)^c(a+bi)^{di}$, we see that raising a complex number to a complex number represents a certain exponential stretch or compression from the origin, followed by a certain rotation.

**tl;dr: You can write $(a+bi)^{c+di}$ to be of the form $(x+yi)e^{\theta i}$, which means take the complex point $x+yi$ and rotate it $\theta$ radians counter-clockwise around the origin of the complex plane.**

(Apologies for the rawness of the explanation... I'd really like to clean this up down the road and put in some pictures. Hope someone thinks it's useful, though!)
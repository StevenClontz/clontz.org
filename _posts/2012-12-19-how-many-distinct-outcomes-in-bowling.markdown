---
layout: post
title: "How many distinct outcomes in bowling?"

date: 2012-12-19 22:59

---

Today I played my final game of bowling in the "Math Nerd League 2012". And maybe my first - I don't know if that moniker was in use before today, but it was used to designate the group of my colleagues in the [Auburn University mathematics graduate program](http://math.auburn.edu/) who went this afternoon.

I'm pretty bad at bowling (although since playing a fair bit this year I've improved my average to roughly 80 compared to a dismal 50). So to keep my mind on happier thoughts, I asked the question:

<blockquote>How many different outcomes are there for one game of bowling?</blockquote>

<!-- more -->

Okay, so, let's remember how a game of bowling works. There's ten frames, and in the first nine frames you get up to two rolls to knock down ten pins. If the first roll knocks down all ten pins, it's a "strike" and there isn't a second roll. We're going to ignore which specific pins are knocked down, including whether the frame is "split" or not, and only consider how many pins are knocked down on each roll, i.e., what's important for scoring.

<small>(A split is normally marked on the score when, after the first roll, the remaining pins don't include the front pin, and are split into two or more nonadjacent groups. It doesn't affect the point total for the game though.)</small>

http://i.imgur.com/E6xqD.jpg 'Results from bowling with some friends back in 2006; 58 was a good score for me at the time.'

So, on these first nine frames, the ball is rolled down the lane, and zero to ten pins are knocked down. Let's say the first roll hits $n$ pins. That means there are $10-n$ pins remaining, and we could hit any number of those (including 0), yielding $11-n$ possibilities. Adding them all up, we get
$$\sum_{n=0} ^ {10} (11-n) = \sum_{n=1} ^ {11} n = 66$$
possibilities per frame.

The final frame is more difficult. The rules change so that if the pins are all knocked down, the bowler gets to roll again, up to three total rolls. It makes sense when you consider how bowling is scored, but we won't go into that here.

Ignoring strikes and spares there are $\sum_{n=1} ^ {10} n = 55$ ways to knock down zero to nine pins in two rolls. There are ten ways to get a spare (knocking down all pins in two rolls), and then there are 11 different possibilities for the final roll (hitting zero to ten pins), so this adds $110$ possibilities.

Finally, if there's a strike on the first bowl, you have $\sum_{n=2} ^ {11} n=65$ possibilities for the next two rolls besides a strike. And finally, if there's a strike, there's $11$ possibilities for the final roll. So the final frame has $241$ total possibilities.

So, looking at the entire game, we can figure out the total number of possibilities by multiplying the number of possibilities per frame. So that gives us... $$66 ^ 9 \cdot 241 \approx 5.73 \cdot 10 ^ {18}$$ possibilities.

Long story short, there's a lot of bowling I have left to do before I've seen it all.

-SXC
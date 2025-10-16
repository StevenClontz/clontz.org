---
layout: post
title: Fun in my Math in Society Class
subtitle: gotta bounce!
header-img: "img/teaching-bg.jpg"
date: 2025-10-16 16:28
---

Today was a lot of fun in my MA111 "Math in Society" course, which is taught from
[Math in Our World: A Corequisite Approach (Sobecki & Mercer)][0] (not an endorsement;
y'all know I'd prefer an OER, but I haven't had a chance to source or write one aligned
with our learning outcomes).

In **Lesson 2-7 Follow the Bouncing Golf Ball**, the authors suggest an activity where
students drop a golf ball from 250cm, record its average bounce height after three trials,
then repeat this process by dropping the next three from that average, and so on. What's nice
about this is that it models an exponential decay function, but I thought it was lacking in
motivation for the students.

So I ran things a little differently. This morning at 7am, I went to their classroom and
dropped ten golf balls from the ceiling (101 inches high), and measured their bounce heights.
I computed the average on my phone calculator, took a screenshot, and successfully forgot
what it was by the time I taught at 2pm.

When class begin, I gave the students the same golf balls, and told them they had 30 minutes
to work together to collect data. The only catch was that they were not allowed to release the
golf balls any higher than the classroom whiteboards, about 84 inches off the ground.

They ended up collecting this data: [`golf-ball-data.csv`](/assets/20251016/golf-ball-data.csv).
And I'm really excited to report that they were able to use a linear model, using the line
of best fit, to make a prediction of 74 inches for the ball to bounce if released from
the ceiling. Given that the actual average was 75.3, that's not too bad! (Actually, I'm wondering
if my records might have overestimated, given that I was looking down at the tape measure at
a bit of an angle...)

![Screenshot of scatter plot generated from the data points collected by my students. The drawn line of best fit is labeled with its equation: 0.641*x+9.28](/assets/20251016/image.png)

Overall it went really well; definitely the best day of class so far. Thoughts for next time:

- I should have just waited and did my bounces at the end of class with their help. That might
  have been an even better reveal than just telling them what I did that morning.
- I think I know what I'll do for the make-up: I can set up a tape measure and record a ball
  bouncing ten times in front of it without interference. But I'll only share the video of
  the first eight bounces with the class - they could use an exponential decay model to predict
  the hight of the last bounce.

[0]: https://www.mheducation.com/highered/product/loose-leaf-math-in-our-world-a-corequisite-approach-sobecki.html

---
kind: article
title: "Randomly selecting a line of input with uniform distribution without knowing how many lines to expect"

created_at: 2013-01-29 10:44

---

Man that title is a mouthful. The concept is simple, but putting it to words takes a bit of work (I think - let me know if you can put it more succinctly!).

The idea is lifted wholesale from this [/r/math post](http://www.reddit.com/tb/17fnb2), which is a cool concept (albiet poorly written). I've tried to make it a little more digestable in [this comment](http://www.reddit.com/r/math/comments/17fnb2/an_algorithm_to_randomly_select_an_item_from_a/c85bifv) (careful, spoilers!), which I've copied below (without spoilers).

<!-- more -->

> You are the head of a casting agency, and need to select an actor for an upcoming commercial. A line of auditioners are outside your office, and you've decided that you do not care which person is chosen. You're a fair person, so you would like a method to randomly choose an actor such that each actor has equal probability of being chosen. However, since your office doesn't have windows, you're only able to see the person at the front of the line (so you cannot tell the length of the line). In addition, your office only fits two people including yourself, and once someone leaves the line or your office they won't return. Can you find a method that works?

Since I started sitting in on an Advanced Programming course here at Auburn, I've gotten into these programming puzzles, particularly where the solution is at the intersection of programming and mathematics. That's essentially what this is after all:

* You expect a stream of input (let's say unique strings split into lines, and no more than 10000 of them).
* You only have enough memory to store one line of input at a time, and an integer. (Why? Because.)
* You want to print a *random* line out of the input, with uniform distribution. That is, the first line of input has the same probability of being printed as the last line, as the middle line, as the 23rd line, etc.

Now, if we were able to store the whole stream of input, there's no problem. Quick python solution:

    foo = ['a', 'b', 'c', 'd', 'e'] # captured earlier from input
    import random
    print random.choice(foo)

Maybe that's a case of [import antigravity](http://xkcd.com/353/), but solutions in any other languages should be similarly simple.

However, the above solution requires storing the entire stream of input, and we are forbidden from doing so. Basically, as we're fed each line, we have to either store it (and remove all knowledge of any previously stored line), or ignore it forever. How could we possibly know whether we're going to choose the 1st guy, or the 2nd guy, or the nth guy, without seeing them all?

It's a great puzzle. See if you can figure it out. The solution is below.

http://i.imgur.com/pImDAzc.jpg This space intentionally left blank.

The hint (or maybe red herring?) above was this sentence: "How could we possibly know whether we're going to choose the 1st guy, or the 2nd guy, or the nth guy, without seeing them all?" Because you can't, obviously. You require that you choose a particular line with probability 1/len(foo). So you need to know the length of foo before you finally make your decision.

But since you can't go back to previous strings in the input, you gotta get creative. And here's where the math comes in. Here's my solution:

```
# only variables I'm allowed to store/modify
i = 0
stored_string = "No input given!"

# we'll need to be able to make random choices
import random

# solution
while True:
  try:
    i += 1 # count the place of this string/person in line
    if 1 == random.randint(1,i):
      # make a decision to keep it with probability 1/i
      # note for first person, i=1, so this passes
      stored_string = raw_input()
    else:
      # otherwise ignore it
      raw_input()
  except EOFError: # ran out of people in line, we're done
    break

# Claim: the line stored had equal probability of being chosen with any other line
print "Result:\n%s" % stored_string
```

Try it out - it *looks* like it works. But why? I should prove it.

The proof is simple - let's assume the length of the input is $n$ lines, and we should show the probability of printing the $i^{th}$ line is $\frac{1}{n}$. Then...

> P(printing $i$) = P(storing $i$) x P(not storing $i+1$) x ... x P(not storing $n$)

Mathematically, this translates to:

$$ P(\text{printing }i) = \frac{1}{i} \times \left(1-\frac{1}{i+1}\right) \times \dots \left(1-\frac{1}{n}\right) $$

$$ = \frac{1}{i} \times \frac{i}{i+1} \times \dots \times \frac{n-1}{n} = \frac{1}{n}$$

So cool.

-SXC
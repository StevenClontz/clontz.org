---
kind: article
title: "Guessing passwords"

created_at: 2012-12-17 11:18

---

There's not any deep cryptography going on here, but since I spent 15 minutes answering this person on [/r/askmath](http://www.reddit.com/r/askmath/comments/14zzhw/i_guessed_the_password_on_my_moms_computer_snot/), and nobody reads /r/askmath, I'd take the time to cross-post it here.

The question:

<blockquote>I guessed the password on my Mom's computer. "Snot". This isn't relevant to anything I can think of in the last 10 years. What are the chances of my guess being correct?</blockquote>

<!-- more -->

---

Depends on the constraints on this password. If you knew it was exactly four lowercase letters (no numbers, no symbols), there are 26^4 = 456,976 possibilities. That makes it a 0.00022% chance.

More realistically, if you knew that the password was a four-letter Scrabble word, there are somewhere around 4,000-5,000 possibilities, so your odds just jumped to 0.02%.

But. If your mother was clever and mixed uppercase and lowercase letters, that increases the number of possibilities by 16 times. (Why? Multiply by two for the first letter being uppercase or lowercase, multiply by two for the second letter, and again, and again. 2\*2\*2\*2=16.) That means we have about 80,000 possibilities, and a 0.00125% chance.

Of course, as soon as you throw out the four-letter constraint, the possibilities explode. But let's keep the Scrabble word constraint. According to the [Official Tournament and Club Word List article on Wikipedia](http://en.wikipedia.org/wiki/Official_Tournament_and_Club_Word_List) there are 178,691 Scrabble words, so we're back down to 0.00056% for one go, and that's assuming all-lowercase.

Finally, just for kicks, let's assume all you knew is that the password is somewhere between 1 and 20 characters, and could contain lowercase, uppercase, digits 0-9, or any of the special characters !@#$%\^&\*(). That's 72 possibilities for each character, which Wolfram Alpha informs me gives [14,214,254,150,091,658,100,874,779,924,350,129,800](http://www.wolframalpha.com/input/?i=%5Csum_%7Bi%3D1%7D%5E%7B20%7D+72%5Ei) possibilities, with a 0.000000000000000000000000000000000000007% chance of guessing correctly.

tl;dr: you got lucky. But keep in mind that I'm not surprised that out of the millions of users on Reddit, someone got this lucky. After all, people win the lottery all the time - just not me.

---

-SXC
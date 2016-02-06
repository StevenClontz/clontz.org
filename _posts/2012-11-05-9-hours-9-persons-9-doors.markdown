---
layout: post
title: "9 Hours, 9 Persons, 9 Doors"

date: 2012-11-05 13:33

---

Having spent a lot of my weekend playing it (after representing Teloga at the [26th Annual Auburn Alumni Band Reunion](http://teloga.com/networks/aubands/alumni-band/fall-2012/)), I wanted to make a quick, mostly spoiler-free post about [*999: 9 Hours, 9 Persons, 9 Doors*](http://en.wikipedia.org/wiki/999:_Nine_Hours,_Nine_Persons,_Nine_Doors) (2010). It's a visual novel / room escape / puzzle / adventure game for the Nintendo DS.

<!-- more -->

http://i.imgur.com/8xVM5.jpg

While I was mostly a Nintendo kid, I have fond memories of playing Sierra's [Torin's Passage](http://en.wikipedia.org/wiki/Torin's_Passage) on the PC, which jump-started my interest in story-driven and combatless games. These games are also probably a big influence in my taste in [story-driven puzzle parties](http://auburnpuzzleparty.wikia.com/wiki/APP5) as well.

The concept of *999* is simple: big scary guy ("Zero") in a gas mask kidnaps you and eight other people, forces you to play a [game](http://en.wikipedia.org/wiki/Saw_(film\)), and slaps a wristwatch on you that will kill if you break the rules rather than solve his puzzles. But the best part of the game is tough to explain without spoilers. I'll just say: it has the best setup for alternate endings of any game I've played.

By the way, I was very impressed that the game doesn't shy away (too) much from using math. There's a bit of modular arithmetic involved in the game: each player has a number on their bracelet, and several doors are also marked with numbers. In order for a group to pass through a numbered door, the "digital root" of the bracelets (more commonly known as the sum of the numbers modulo nine) must match that number. This makes a major part of the story a mathematical whodunit once the group splits up early on and it's discovered that some subset of them opened a door secretly (to a particular end which I'll keep secret for this post).

I do wish the characters would have caught onto some of the slicker tricks to computing digital roots. For example, the players 1 through 9 have a digital root of 9. But if players 1 and 2 are sitting out for some reason, the group's digital root is now 6. That means for all players to progress simultaneously, they must split up and pass through doors whose digital root is also 6. The characters make most of their conclusions through exhaustive search, but when I was faced with doors 3, 7, and 8, I quickly realized that 7 & 8 (=15=6) were the only real choices. (Well, unless you wanted to leave some players behind, but who would do that?...) And the only trick then was finding a group to sum to 7 (or 16 or 25), since the other group necessarily had to sum to 8 (or 17 or 26 or etc etc).

Incidentally, while I keep talking about modular arithmetic, the game didn't present it that way. Instead, they used the divisibility trick for nine to describe how to calculate a digital root: add the digits of the sum, repeat until only one digit remains. All in all, it's a fun metapuzzle for the game. (And not bad fodder for the [AMP'd Challenge](http://auburnpuzzleparty.wikia.com/wiki/A.M.P.%27d_Challenge) either... maybe I should flesh out an idea based on this.)

But about those endings. There's a lot of discussion out there about the optimal way to play through the game. There are six (well, five and a half) endings that the game gives you credit for, and it's tough to find them all without a little direction (which I attempted when I first played through the game two years ago). So if I may do so, and I promise not to reveal any spoilers, here are my two suggested ways to play through *999* if you have the chance to pick it up.

###What you should know

In this game you will make three choices between which door you'd like to enter. If you get a "bad end", which one you get is pretty much just determined on your third choice. The game intends for you to play through it multiple times and stumble upon one of the three ends which, well, aren't so bad.

However, by paying attention to what interests the other characters, and figuring out which doors you need to go through to progress certain story arcs, you can arrive at one of the three more interesting ends. Realizing this might be enough for you to deduce how to proceed.

###The quickest way

You should approach *999* more like you're going to read a book than play a game, which means you'll be spending a lot of time reading. And on the replays, you'll be spending a lot of time holding Right on the D-pad to fast-forward through text you've already seen.

So that's why I don't blame you if you want to get through things as quickly as possible. Here are directions for seeing every puzzle and ending using minimal playthroughs:

<p class="spoiler">1st. Choose the following doors: 4, 8, 1</p>

<p class="spoiler">2nd. Choose the following doors: 4, 7, 6</p>

<p class="spoiler">3rd. Choose the following doors: 5, 3, 2</p>

<p class="spoiler">4th. Choose the following doors: 5, 8, 6</p>

At this point, you may want to try and solve the puzzle of which path to take for your final ending. Pay close attention to a hint given at the end of the last ending.

<p class="spoiler">Last. Choose the following doors: 4, 7, 1. This unlocks the final two endings (one of which is where the game cuts off this ending early if you haven't done the 5, 8, 6 ending). Also, you need to be sure to learn everything you can from the other characters, and help them out where you can, or certain story checks will fail and you'll get the same ending as choosing 4, 8, 1.</p>

###A little bit longer

This is a streamlined version how I ended up playing my first time with the game. There's more backtracking, but you get to actually experience that "half" ending I keep talking about.

<p class="spoiler">1st. Choose the following doors: 4, 8, 6</p>

<p class="spoiler">2nd. Choose the following doors: 5, 3, 2</p>

<p class="spoiler">3rd. Choose the following doors: 4, 7, 1. However, refuse to listen to optional plot points and don't help the other characters when possible.</p>

<p class="spoiler">4th. Choose the following doors again: 4, 7, 1. This time, listen to everything and help a certain person out.</p>

At this point, you may want to try and solve the puzzle of which path to take for your next ending. Pay close attention to a hint given at the end of the last ending.

<p class="spoiler">5th. Choose the following doors: 5, 8, 6</p>

<p class="spoiler">Last. Choose the following doors a final time: 4, 7, 1. Again, listen to everything and help a certain person out. Enjoy the epiphany.</p>

###And every other combination

I ran across this image on Reddit, which maps out all the possible paths and endings. Pretty cool to look over once you've seen them all yourself: <http://i.imgur.com/amjI5.gif>

That's all I've got. If you've gotten this far then I assume you've played the game or plan to. But if not, and you think you'd enjoy this psychological thriller, then I encourage you to give it a try! (Also, the sequel came out... maybe I'll have time to play it one day, heh.)

-SXC
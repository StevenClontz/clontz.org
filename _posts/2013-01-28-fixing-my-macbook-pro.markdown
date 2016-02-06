---
layout: post
title: "Fixing my Macbook Pro - replacing hard drive SATA cable"

date: 2013-01-28 16:12

---

So, about two weeks ago [I found myself without a working hard drive](https://www.facebook.com/steven.clontz/posts/10101144733985781) on my Macbook Pro (13", mid-2008). That's what I thought anyway [until the hard drive turned out to work fine in an external enclosure](https://www.facebook.com/steven.clontz/posts/10101146355955341).

As it turned out, the fix was simple - replace the SATA cable connecting the hard drive to the logic board. But figuring out that was the problem/solution was a little frustrating, so I wanted to outline what happened here so that someone else may trip across this one day and find it helpful.

<!-- more -->

The symptoms were simple: I opened my computer out of sleep one Saturday only to discover that while the computer was up and running, it was stuck trying to load something that it never could. This resulted in a pretty spinning rainbow-colored circle that I could move around my screen, but not much else. As it turned out, the OS was trying to access the hard drive, but the cable connecting it to my logic board had given up the ghost.

Upon restarting the computer, the Apple logo appeared on the gray screen, along with the spinning gray wheel like it was trying to load the OS, but five minutes resulted in nothing.

Booting from the Snow Leopard install DVD let me access the Disk Utility. I attempted to unmount the hard drive, but was informed that I could not due to either an "input/output" error, or "could not allocate memory". This prevented me from wiping the drive, which I felt at the time was a good attempt to solve the problem (having backed up with Time Machine earlier in the week).

I decided to purchase a new hard drive from Best Buy, but after trying both a Seagate and a Western Digital, I realized I was likely barking up the wrong tree. I borrowed a 3.5 inch SATA external enclosure, carefully installed my 2.5 inch SATA drive, and hooked it up to my laptop via USB. Lo and behold, Disk Utility could easily format the disk and reinstall OSX from the Time Machine backup!

I managed to use my computer on "life support" by booting from the external enclosure for two weeks. The 3.5 inch enclosure didn't properly secure the hard disk and required external power, so I ordered a 2.5 inch enclosure for just a few bucks here: <http://www.amazon.com/gp/product/B002JQNXZC/ref=oh_details_o00_s00_i00>

Meanwhile, seeing as the hard drive seemed to be functioning fine, I banked on the issue being with the SATA cable connecting it to the logic board. (A friend pointed out it may actually have been an issue with the board itself, but I didn't want to entertain that ugly possibility.) Coincidentally, there is a shop in Huntsville, AL that let me order just what I needed online: <http://www.powerbookmedic.com/Hard-Drive-Cable-w--IR-Sensor-for-MacBook-Pro-13-Unibody-p-17336.html>

However, when it came in, it was just a few millimeters too short - I had ordered the wrong version of the part! Everything would plug in fine, but there just wasn't enough room for play. I should have taken photos at the time, but here's how things are supposed to look, taken from instructions on how to remove the battery:

http://i.imgur.com/l5injMs.jpg

Now, see that cable just above the left circle? that's the cable connecting the hard drive to the logic board. You can see that it lays flat on the optical disc drive. You can probably imagine the trouble if it were just a tad short.

My solution? I was able to make a snip on the cable over a hole where it was intended to be screwed into the casing to be secured. That slight modification allowed me to connect everything. You can see a similar cable below - the holes on either side of the cable were in the way, but if you don't mind mutilating your cable, they can be cut off with an ordinary pair of scissors without harming the actual wires inside.

http://i.imgur.com/WM4THZf.jpg

With the new cable installed, my computer now runs good as new. Although I have to admit I was surprised how nicely the computer ran off of the external USB enclosure as well - just be careful not to remove the USB cable while the computer is running in that case! I managed to accidentally do that a couple of times, which just locked up the computer until I reset thankfully.

-SXC

ADDENDUM 2013/01/29: A friend just had the same issue! Punchline: she went to the university bookstore, who waived any labor fees and just ordered the cord for $25. Ahhh well, now I know to ask them first next time. :)
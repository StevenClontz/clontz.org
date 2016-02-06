---
layout: post
title: "GradeCalc"

date: 2013-11-04 20:57

---

It's been way too long since I updated, but I wanted to share the revival of my most popular app: [GradeCalc](http://gradecalc.stevenclontz.com). Development notes follow.

http://i.imgur.com/DEiiWaH.png

<!-- more -->

I'd been thinking about updating my aged [Dead Day Grade Calculator](http://www.auburn.edu/~clontsc/deadday-archive.php) for a while now - for such a simple app it seemed that a static Javascript-powered site was the way to go.

But there was no way I was abandoning conveniences like [Slim](http://slim-lang.com/) or [CoffeeScript](http://coffeescript.org/) to write out all the HTML and JS by hand. Enter [nanoc](http://nanoc.ws/) - I can develop in Slim/LESS/Coffee, and then Guard automatically generates static HTML/CSS/JS. I set up a separate Git repo in the `/output` folder to push to `gh-pages`, took about five minutes to set up the subdomain, and in about ten hours I had set up a site far more polished than my sad PHP-powered 2008 attempt.

I'm happy to hear any feedback! Shoot me an email at <steven@clontz.org>. (Yup that's new.)
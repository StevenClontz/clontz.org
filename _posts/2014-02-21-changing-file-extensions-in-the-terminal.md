---
kind: article
title: "Changing file extensions in the terminal"
created_at: 2014-02-21 17:01
---

So I can't exactly publish this while I'm in the middle of moving my site
to [nanoc](http://nanoc.ws), but here's another bash one-liner for 
mass-changing an old extension `*.old` to a new one `*.new` within a folder.

~~~
for file in *.old; do mv "$file" "${file%.*}.new"; done
~~~

Pretty useful: I wanted to change from Octopress's `*.markdown` extension to
the more typical `*.md` for my blog posts, and that saved me a few clicks!
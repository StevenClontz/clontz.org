---
kind: article
title: "Marked-down resume"

created_at: 2012-10-28 23:30

---

A project that had been almost as long overdue as reviving <http://www.stevenclontz.com> was updating my neglected resume.

The tl;dr version: check it out at <http://resume.stevenclontz.com>! But if you think that looks nice and would like to check out the web app that powers it, please read on. :-)

<!-- more -->

I knew I wanted my resume to be web-first. The last time I wrote a resume (back in early 2011) I had TeX'd it up locally. And hey, at least that's better than a Word document, right? However, and maybe I've gotten lazier in the past two years... but trudging through this didn't seem appealing:

```
\begin{ressection}{Education}
    \begin{ressubsec}{Auburn University}{Auburn, AL}{Bachelor's of Science and Master of Science in Mathematics}
        \ressubitem{Undergraduate GPA: 3.88 (overall), 4.00 (Major)}
        \ressubitem{Undergraduate Graduation Date: May, 2008 (Summa Cum Laude, University Honors Scholar)}
        \ressubitem{Masters GPA: 4.00}
        \ressubitem{Masters Graduation Date: December, 2010}
        \ressubitem{Currently pursuing Doctor of Philosophy in Mathematics at Auburn}
    \end{ressubsec}
\end{ressection}
```

So began my search for a simpler way. My first instinct was [Markdown](http://daringfireball.net/projects/markdown/) - it's what [Teloga](http://www.teloga.com) uses, it's what [Reddit](http://www.reddit.com) uses, heck, it's what this blog uses. And certainly this markup is a lot friendlier to read and edit:

```
##Education

####Auburn University - Auburn, AL

* Bachelor's of Science in Mathematics (2008)
    * 3.9 overall GPA | 4.0 major GPA
    * Summa Cum Laude | University Honors Scholar | Phi Kappa Phi | Phi Beta Kappa
    * Honors thesis in unfoldings of convex polyhedra | Undergraduate Research Fellow
* Master of Science in Mathematics (2010)
    * 4.0 GPA
    * Master thesis in linearly ordered topological spaces
* Doctoral Candidate in Mathematics
    * Currently writing dissertation on limited information strategies in topological games
```

So I thought the simple thing to do would be to just make a page on this blog for the resume. And when I did, it didn't look half bad either.

http://i.imgur.com/U6xQ4.png

The only problem... I'd probably need a PDF version as well, and maybe even have to print it at some point. Silly old media.

Now, keeping multiple copies of the same resume definitely violates [DRY](http://en.wikipedia.org/wiki/Don't_repeat_yourself); I wanted a slicker solution. So my first idea was to just print the webpage from Chrome and save it as a PDF.

http://i.imgur.com/kdRdF.png

Yikes.

So, the issue that Octopress's default theme doesn't have a nice print stylesheet is a topic for another day, but I figured there was someone else out there of a similar mind that would have already paved the way for a nice way to share a resume written in Markdown.

As it often does, the Google helped me find an answer earlier today: <http://pseudoweb.net/2010/10/25/developing-your-resume/>

http://i.imgur.com/nAmTh.png

Looks nice, and it prints well too. Incidentally, Mr. Welch's resume app makes use of this very cool Ruby gem called [Sinatra](http://www.sinatrarb.com/) which I may need to look more into for simple apps. I'm new to Ruby (hey maybe I can add it to my resume now though) but hacking his app to do what I wanted was pretty straight forward.

I added a few extra variables to the configuration YAML to store the URL of the page itself and the URL of a QR Code image leading to that URL, which I use in a couple of nice extra features:

1. If the page is printed, it adds a line to the top: "Optimized for web | http://resume_url"
2. A QR code floats in the upper right of the page, also linking to the digital version of the resume.

http://i.imgur.com/2WrpD.png

You can see it in action at [my resume page](http://resume.stevenclontz.com), and my forked version of the app can be found [on my Github](https://github.com/StevenClontz/Resume).

There are still a couple of tweaks that might be nice to have if I decide to work on this more later.

- It'd be preferable to have a script to burn a PDF from the resume.md Markdown file rather than using a browser printout, possibly leveraging LaTeX.
- A simple change would be to move some of the basic data (name, address, etc.) into the configuration file to standardize the header.

In the meantime, I hope you found all this interesting, and maybe I've inspired you to use revision control and Markdown to maintain your own resume!

-SXC
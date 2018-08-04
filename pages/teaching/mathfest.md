---
layout: page
title: "MathFest"
description: "materials for MAA MathFest 2018"
header-img: "img/teaching-bg.jpg"
permalink: /mathfest/
---

I will be co-organizing two workshops and giving
one individual presentation at MAA MathFest 2018.
Please contact me at <sclontz@southalabama.edu> with any questions!

## Workshop: An Introduction to Team-Based Learning

*Drew Lewis and Steven Clontz*

Participants are encouraged to review the following "readiness preparation materials" 
(a component of Team-Based Learning), to introduce them to the basic
ideas behind Team-Based Learning.

- <https://cft.vanderbilt.edu/guides-sub-pages/team-based-learning/>
  - *est. time: 6 minutes*
- <http://www.celt.iastate.edu/teaching/teaching-format/team-based-learning>
  - *est. time: 4 minutes*

Time estimates calculated using [Niram.org](http://niram.org/read/).

After the workshop, you may be interested in the following resources:

- [PDF of workshop slides](/img/20180802/tbl-mathfest.pdf)
- The [GitHub project](https://github.com/StevenClontz/tbil-la) for our
  in-development
  TBIL Linear Algebra resources.

## Workshop: Mathematical Puzzle Programs: Outreach and Recruitment with Puzzles

*Braxton Carrigan, Steven Clontz, and PJ Couch*

Participants in this workshop will get to play an abbreviated version of the
MaPP Challenge competition for themselves. If possible, please bring
an iOS or Android smart device with internet access to play along using
the [ClueKeeper](http://cluekeeper.com) app.

Please visit [MaPPmath.org](http://mappmath.org) for more information
on Mathematical Puzzle Programs.

Theh puzzles for this workshop are available on our GitHub:
<https://github.com/MaPPmath/challenge18/blob/mathfest-demo/mapp-challenge-18-game-book.pdf>

## Presentation: Tools to Facilitate Mastery Grading 

I will review two web applications I use for mastery grading.

- [sbg-rails](https://github.com/stevenclontz/sbg-rails/)
  - This app is being written by myself using Ruby on Rails. Anyone comfortable
    with running a Ruby on Rails app may clone and install the repo
    using the GitHub link above.
  - A (buggy) demo is available at <https://sbg-rails.herokuapp.com/>.
    It requires a username/password provided at the presentation.
  - The app is designed around two goals:
    - Instructors are given an interface to efficiently log student attempts to
      master course standards, and produce progress reports based on those attempts.
    - Exams may be custom generated based upon student progress and a problem bank.
  - To enter grades, a spreadsheet-like interface is provided. However, this is
    still somewhat inconvenient as assessments need to be graded on paper
    and then re-entered exercise-by-exercise into the app.
- [Gradescope](https://gradescope.com/)
  - Currently, the Gradescope Basic plan is available for free to the first five instructors
    from each institution who sign up; later signups get two terms free.
  - Instructors can create and grade arbitrary worksheets using this app.
  - While it's designed around traditional grading, it can still be used
    to support a mastery grading classroom.
  - My implementation: use sbg-rails to generate assessments, and students submit
    answers on sheets that I upload to Gradescope.
    - Answer sheet: [PDF](/img/20180731/answer-template.pdf)
    - Sample responses: [PDF](/img/20180731/sample-solutions.pdf)
  - By "exporting evaluations", spreadsheets for each graded standard may be exported from
    Gradescope and copied/imported into your gradebook of choice. sbg-rails has
    an import utility for Gradescope reports.

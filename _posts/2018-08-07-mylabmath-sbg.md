---
layout: post
title: "SBG in MyLabMath"
subtitle: "using the Study Plan"
header-img: "img/teaching-bg.jpg"
date: 2018-08-07 21:48

---

In response to a [discussion][discussion] on Twitter
with Kate Owens and Drew Lewis,
I wanted to document my experience using the Study Plan
in Person's Study Plan feature within its MyLabMath
(MyMathLab? MyLab Math?) product.

For various reasons outside the scope of this blog post, 
I chose to make the [course][course]
(click for the syllabus) grade 85% based on the Study Plan,
and 15% on the Final Exam.
With 85% based on the Study Plan, I of course needed to ensure two
things:

1. Completion of the Study Plan should reflect true mastery
   of the course objectives.
2. I should be able to reasonably guarantee that academic honesty
   had been respected by my students.

For #1, I began by reviewing my options. In the Study Plan,
instructors can see a master list of all "objectives" by visiting
`Study Plan > Manage > Coverage and Scoring`. Each objective may be
selected as `Scored and recommended` (counts towards the Study Plan grade) 
and/or `Available for practice` (appears in the student Study Plan).
In my implementation, I always used both options together (and I'm not sure
why anyone wouldn't at least include all scored objectives in practice), 
so I won't distinguish them further here.

To design my course, I went through and first checked/unchecked the sections
of the textbook that my [department course syllabus][dept-course-syl]
designated. Then within each section, I checked/unchecked objectives
according to the following criteria:

- I covered all the "learning objectives" given on my department's course
  syllabus.
- Even if it wasn't explicitly given as a "learning objective", I included
  objectives that either supported future objectives or I simply thought
  were important.
- I tried to limit myself to four or less objectives per section, with
  five as my absolute maximum.
- There existed multiple reasonable exercises for students to complete
  when practicing and being assessed in MyLab Math.

Per the last point: each objective can be expanded into its supporting
exercises in MyLab Math. Often, many of the exercises were either too easy
or too perfidious to be worthwhile as either practice or assessment.
(I suppose there's an argument to only include these in practice; I chose
not to.) So I selected the exercises that seemed reasonable tractable and
relevant for assessment; there were a few interesting objectives I
abandoned due to a lack of quality exercises.

Here is where I diverged from the intended use case of the Study Plan.
Pearson, for some unintelligible reason, has designed the Study Plan as
though only the student is interested in knowing their mastery of course
material. So while there is the ability for instructors to see Study
Plan progress and use it as a part of the grade on MyLabMath, there are
~~two~~ three serious anti-patterns in Pearson's design (that I've reported to them,
not that I anticipate any changes):

- *UPDATE 2018-08-08:* **Study Plan mastery is set by student account, not by
  the course.**

This isn't bad in of itself, but the only way to fairly assess based on
work done during your course is to enable an option in the Study Plan to
scrub all previous progress in the Study Plan from previous semesters. I wish
there was a way to have a course-level Study Plan that somehow shadows the
student-level Study Plan. There's possibly a major security issue here if a student
has access to a second MyLabMath course that can improve the Study Plan;
that depends on how Pearson has implemented things behind the scenes and
I cannot tell.

- The default/natural way to configure the Study Plan for students to
  demonstrate mastery is through a "Quiz Me" feature. After students
  click the "Practice" button and correctly solve a few relevant exercises,
  the "Quiz Me" button becomes available, which generates a random quiz
  based upon that sole objective.
  **There is no way to password-protect this feature.**

Of course, the above issue directly contradicts Thing #2 listed above. Fortunately,
this can be disabled. Instead, students can be required to instead answer a relevant exercise
from an assigned assessment via `Study Plan > Manage > Mastery`. This brings up the
second anti-pattern.

- Pearson expects instructors to design their assessments first, and then generate
  Study Plans based upon those assessments. 
  **This is in conflict with [backwards design][back-des]†, and there is no automatic
  way to generate assessments from a carefully curated Study Plan.**

However, despite the shrugging I got from Pearson when I asked, I did find a way
to hand-create assessments from an existing Study Plan without too much pain.

- I created a quiz for each section (or two sections if they summed to four/five objectives)
  using `Assignments > Manage > Create Assignment`.
- I named the quiz for that section(s), and did not create a companion Study Plan
  since I already had done that work at the beginning as a part of my backwards design.
- Under `Add/Remove Content`, I chose the Chapter and Objective, and then under Availability
  I chose "Questions that are in the Study Plan".
- Then for each Objective that would list questions (which were in my Study Plan),
  I hit the "check all" box and clicked "Pool" to create a quiz exercise that would be
  chosen randomly from that pool.
- I set a password for the quiz and let it be available for the entire semester.
  *UPDATE 2018-08-08:* Quizzes could be attempted infinitely many times.

Since a password was set, students were required to visit our on-campus Math Technology Lab
to complete quizzes. For this summer MTWRF class, I actually did not cover new material
on Fridays to let students visit the lab and work on quizzes. They could also reclaim
their Friday afternoons to do other things, and work on quizzes at another time during
the week that the lab was open as well. (I made an error here: I should have required students
to either spend a sufficient amount of time or made a sufficient amount of progress 
in the lab working on quizzes in MyLabMath, since I believe
that data is available, or else they should have been forced to come to class on Friday.)

*UPDATE 2018-08-08:* In the gradebook, there were only two entries: 85% for the Study Plan,
and 15% for the Final Exam. Note in particular that Quizzes were worth 0% directly, but
they updated the Study Plan, so each correct response was essentially
worth about 1% of the overall grade for the course.

Overall I think this went well. A major downside was the inability to assess twice in
MyLabMath: while I don't usually consider a standard "mastered" until it has been
demonstrated as mastered twice on separate weeks, there's no way to enforce this in
MyLabMath directly (as far as I know). So this was part of the justification for the final,
as students knew they would need to hit the high points of the course one more time
at the semester's end. However, because the final was so weakly weighted, I'm unconvinced
it was very useful. (Of course, there are other reasons to give a final besides
pedagogical soundness...) My final was given on paper, separate from MyLabMath, and
did not affect the Study Plan at all.

**TL;DR:** Using the MyLabMath Study Plan for SBG is better than using MyLabMath
for pretty much anything else. They could make the product a lot better, but I haven't
been given much evidence that Pearson cares. Given a repeat of the situation I was in
(a short-notice prep for a summer freshman math course), I'd probably do everything
again the same way, with the above noted exceptions.

---

[discussion]: https://twitter.com/katemath/status/1026848341177638914
[course]: https://prof.clontz.org/classes/2018/06/ma125/
[back-des]: https://cft.vanderbilt.edu/guides-sub-pages/understanding-by-design/
[dept-course-syl]: https://www.southalabama.edu/colleges/artsandsci/mathstat/syllabi/ma125.html

<small>† What an unfortunate name: I get that we want to start by thinking about
what our students should master by the end of the course, but "backwards" certainly
comes off as... well, backwards.</small>

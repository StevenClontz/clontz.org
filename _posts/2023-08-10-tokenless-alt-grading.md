---
layout: post
title: "Tokenless Alternative Grading"
subtitle: "balancing encouragement of on-time submissions with grace for late submissions"
header-img: "img/teaching-bg.jpg"
date: 2023-08-10 16:00:00
---

If you're reading this, I probably don't need to convince you of the value of having grace for late submissions, both ethically
and pedagogically, but if I do, I'll let David and Robert take the wheel: [GradingForGrowth.com](https://gradingforgrowth.com/)

That said, a common concern folks share with me: since it's still better for students to not leave all their required work for
the last minutes of a course, how can I balance this grace with encouragement of sticking to the pace of the course as best as a
student can? Indeed, I personally can attest to my early days of alternative grading where I goofed on this a bit, and found myself
in the final week of a course with over a dozen students lined out my office door hoping  to reassess particular learning
outcomes from throughout the semester. But I've designed enough bad courses, puzzles, and games to know that coming up with a policy
that tries to guess how many "tries" a student should be able to have at demonstrating their learning is a tough, if not impossible,
proposition.

So here's my quick implementation guide for how I pull things off these days in order to fulfill these criteria:
- Students can demonstrate that they meet expectations for each learning outcome through the last day of class.
- Students are encouraged to keep to the pace of the class as best they can.
- You don't need a degree in economics to create an intricate "token"-based economy for late submissions or reasessments.
  Instead you can just set "best-by dates" and let your policies more or less handle the rest.

## Assessment workflow

Each learning outcome is taught and assessed in my class as follows:

1. Students engage in activities to learn the material (e.g. inquiry, flipped, active learning, etc.).
2. After those activities, students are provided practice exercises that help them prepare to show their learning on a
future assesment.
3. After submitting some evidence of preparation (e.g. solutions to the practice problems), students are able to attempt
a quiz assessing the learning outcome. Ideally this is on-demand, using e.g. https://checkit.clontz.org/ banks and your
LMS.
    - I usually allow students 2 or 3 attempts on the quiz by default. They can request more as long as the semester hasn't
      ended (and may need to, see below). But this limit serves as a speedbump to discourage re-rolling random exercises to
      get one the student prefers from the bank.
4. After the assessment, the student must submit a reflection on their attempt.
[Here's the form I used in Spring 2023](https://docs.google.com/document/d/17gHKQXShBkMZq-8L-dEBLHw-d9azAFYxDVTAVaajHCA/copy)
(and note the `/copy` at the end of the URL to have it open a copy so the student can complete it and download a PDF).
    - At this point, particularly once the student is used to the course, the student may realize they won't meet my expectations
      for showing understanding of the outcome. In this case, the student may not submit a reflection, and return to step 2 or 3.
5. Once I recieve their reflection, I provide feedback\* on their body of work, as well as one of the following marks:
    - ✔️ Meets Expectations (They've demonstrated understanding of this outcome and no further work is required.)
    - ✏️ Requires Further Reflection (A new Reflection incorporating suggested feedback must be submitted.)
    - 💭 Shows Progress but Further Study Needed (A new Quiz and Reflection must be attempted in order to demonstrate understanding 
      of this Outcome.)
    - ❌ Insufficient Evidence of Progress (A meeting with the instructor in office hours is required before reattempting the Quiz.)
    - ❔ Cannot Assess (The Quiz/Reflection cannot be assessed as-is for some reason; follow the instructions given.)
 
## Best-by dates
 
So what's the catch on that **feedback\***? The feedback is generally only provided for a submission that's received before the
"best-by date" for the assignment. Typically, I give students at least a week between when the outcome is explored in class,
and when this best-by date elapses (usually on a Sunday night). I used to give much more time, but students actually gave me
feedback that they *preferred* a shorter time, as they found the option to wait until the last minute too tempting.

This was a bit suprising, given my other policy. I make it clear to my students that, since I have only finite time each week to spend
giving feedback and marks on their quizzes and reflections, I always prioritize submissions that are
recieved in advance of their best-by dates. That is, given two submissions both submitted on September 7th,
one best-by September 10th and the other "best-by" September 17th, I'll provide feedback on the Sep 17 assignment first. Hopefully
I'll get to the Sep 10 assignment as well, because then the student will give feedback and a chance to reattempt the quiz if
needed by its best-by date. But there's not a guarantee.

## After the best-by date

So what's next? First, it should be made clear that I try to give feedback and marks as soon as possible for all on-time submissions
once the best-by date passes. Then, because my best-by dates are not deadlines, students can still attempt and submit work after
they elapse, whether it's because their on-time submission did not meet my expectations, or because they didn't attempt it on time
at all.

In this case, the submissions are marked as "Late" in Canvas. They are still promised to get credit where credit is due, but they are
now on their own to self-reflect and self-evaluate on their attempts without my feedback. They can retake quizzes, and resubmit
reflections, up until they are satisfied in the body of work they are presenting to me. But this is all done without my input or
intervention (other than fielding requests to re-open quizzes, in the rare case that the 3 attempts I provide upfront are
insufficient).

During finals week, I review each student's overall body of work to assign letter grades, using specifications such as:

- A: Earn ✔️ on at least 23 of 24 Outcomes, AND earn three ✔️ from Presentations, AND earn ✔️ on the Final Exam
- B: Earn ✔️ on at least 21 of 24 Outcomes, AND earn two ✔️ from Presentations, AND earn ✔️ on either the Midterm or Final Exam
- C: Earn ✔️ on at least 18 of 24 Outcomes, AND earn one ✔️ from Presentations, AND earn ✔️ on either the Midterm or Final Exam
- D: Earn ✔️ on 12 of 24 Outcomes
- F: Earn ✔️ on less than 12 of the covered Outcomes

Given their performance on Presentations and Exams, their letter grade may be determined by their on-time Quiz submissions. But
if not, I'll review every late submission, as long as the submission would help their letter grade. No feedback is provided to
the student, and these late evaluations cannot be contested: I mark them all privately and just submit the final letter grade
to the university. This is made as clear as I can to students, emphasizing the point that I want them to get credit for everything
they learn, even if they fall behind, but this is another way I can encourage them to keep pace to the best of their ability.

## Wait, you never even peek at the late submissions?

Nah, that'd be a lie. As you can see from my specifications for letter grades, there's a lot of desired activity I want to see
from students (attendance, participation, performance on readiness assurance quizzes that aren't outcomes-aligned) that doesn't
go into the final letter grade. So I hand out late grade reqeuests like candy to encourage that behavior. (I guess you can call
these request opportunities "tokens", but in practice they're hardly used anyway, in contrast with most token systems I've heard
about.)

I also make it well-known that if a student
comes by office hours to discuss a learning outcome, even if it's late, that conversation can sometimes result in my determination
that a student has met expectations for the outcome, and they can get their ✔️ for it that way.

To directly address a concern one friend and colleague had with an early draft of this post: it's not my aim to withold
instructional support from students who miss the arbitrary (in some sense)
best-by date I set for each assignment. In practice, students view the
policy as a reasonable allocation of my finite time; at least, no one has communicated otherwise, directly or through course
surveys.

And also in practice, I'll reiterate what another friend and colleague pointed out: as with any system, you cannot
just let it run on its own. Students will always have extenuiating circumstances, and it's important to reach out to students
who fall behind, and offer appropriate interventions. Then the framework provides a positive context for these conversations.
"I want you to succeed. I'll give you credit for whatever you provide evidence of learning for, as long as I have it
by the time I'm forced by the university to assign a grade. I have many students and a limited amount of time I can spend on
supporting all of you, but let's work together to find what we both can do to get you caught up."

## I ain't reading all that. I'm happy for u though. Or sorry that happened.

TL;DR I make my letter grade specs simple, let folks submit stuff late, but emphasize that my finite time prioritizes early and
on-time submissions. The late stuff always gets credit where credit is due after final exams are submitted,
and there are exceptions where I'll give feedback and marks on late work when appropriate.

Works for me!
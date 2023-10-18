---
layout: post
title: "AMS Sectional Special Session on Math Cyberinfrastructure"
subtitle: "links from today's talks"
header-img: "img/math-bg.png"
date: 2023-10-14 16:00:00
---

[AMS Special Session Details](https://community.ams.org/meetings/sectional/2311_program_ss9.html#title)

- The pi-Base community database of topological counterexamples
    - Steven Craig Clontz, University of South Alabama
    - <https://topology.pi-base.org>
- SageMath for Research and Teaching
    - Kevin Grace, University of South Alabama
- How We Juggled All the Things: SBG + TBIL + CheckIt
    - Abby Noble, Middle Georgia State University
    - Kate Owens, College of Charleston
    - <http://tbil.org>
    - [Link to slides](https://docs.google.com/presentation/d/1tjZNkLplPyYpanPpkzfN0a-1n8FSTdNgMAh7RYkFFbs/edit?usp=sharing)
- Mathematics Education as Outreach for Research in HPC
    - Margaret E Myers, UT Austin
    - Robert A Van De Geijn, UT Austin
- Animating Mathematics in the Classroom with Formative Technology
    - John Estes, Belhaven University
- Enhancing Online Learning Engagement and Support through Scaffolding
    - Jack Ryan Sturm, University of Tennessee, Knoxville
- Manim: Math animation to support teaching
    - Tien Chih, Oxford College of Emory University
    - [Manim Community Wiki](https://docs.manim.community/en/stable/index.html)
    - [TBIL Calculus Video Playlist using Manim](https://www.youtube.com/watch?v=KsemDUSJeWk&list=PLwXCBkIf7xBODPeQxULagMeWSK4YtLYog)
    - (Sample Manim code at the bottom of this post.)

Email me at <sclontz@southalabama.edu> if you're looking for something here that's not up yet!

### Sample Manim code

```python
#%%manim -ql LIPoly

from manim import *
import scipy.stats


class test1(Scene):
    def construct(self):

        title = [0, 0, 0]

        title[0] = MathTex(
            r"\text{A Title }",
            r"x,y, \frac{a}{b}",
        ).scale(0.6)
        title[0][1].set_color(RED)
        title[0].to_edge(UP)

        # title[1] = MathTex(r"\text{Let }-3<c, t<2", color=TEAL ).scale(0.6).next_to(title[0] , DOWN)

        lhs = [0, 0, 0, 0, 0, 0, 0]
        rhs = [0, 0, 0, 0, 0, 0, 0]
        eq = [0, 0, 0, 0, 0, 0, 0]
        caption = [0, 0, 0, 0, 0, 0, 0]

        eq[0] = MathTex(r"=").scale(0.6).shift(UP * 1)
        for i in range(6):
            eq[i + 1] = MathTex(r"=").scale(0.6).next_to(eq[i], DOWN * 3)

        # eq[4] = MathTex(r"\approx").scale(0.6).next_to(eq[3], DOWN*2.75)
        # eq[5] = MathTex(r"\approx").scale(0.6).next_to(eq[4], DOWN*2.75)

        lhs[0] = MathTex(r"x^2").scale(0.6).next_to(eq[0], LEFT)
        rhs[0] = MathTex(r"4y-3\alpha").scale(0.6).next_to(eq[0], RIGHT)
        rhs[1] = MathTex(r"3z-\ln(x^2-y)").scale(0.6).next_to(eq[1], RIGHT)
        rhs[2] = MathTex(r"2z+4w").scale(0.6).next_to(eq[2], RIGHT)
        rhs2a = MathTex(r"2", r"(z+2w)").scale(0.6).next_to(eq[2], RIGHT)

        caption[0] = MathTex(r"\text{A caption }", r"t=3.").scale(0.6)

        caption[0][1].set_color(YELLOW)
        caption[0].to_edge(DOWN)

        self.play(Write(title[0]))
        self.wait(8)

        self.play(Write(lhs[0]))
        self.wait(5)
        for i in range(3):
            self.play(Write(rhs[i]))
            self.wait(3)

        self.play(Transform(rhs[2], rhs2a))
        self.wait(5)
        self.play(rhs2a[0].animate.set_color(PURPLE))

        self.play(Write(caption[0]))

        self.wait(10)


class test2(Scene):
    def construct(self):

        title = MathTex(
            r"\text{A title again }", r"\arctan\left(\frac{t^3-4z}{2\ln(x)-5}\right)."
        ).scale(0.6)
        title[1].set_color(RED)

        title.to_edge(UP)

        # title1a = MathTex(r"y\approx 0.337872x + 64.8387, R\approx 0.8333, R^2\approx 0.6944", color=TEAL).scale(0.7)
        # title1a.to_edge(UP)

        axes = Axes(
            x_range=[-6, 6, 2],
            y_range=[-6, 6, 2],
            x_length=5.5,
            y_length=5.5,
        ).shift(LEFT * 3.5)
        numberplane = NumberPlane(
            x_range=[-6, 6, 2],
            y_range=[-6, 6, 2],
            x_length=5.5,
            y_length=5.5,
        ).shift(LEFT * 3.5)

        tracker1 = ValueTracker(1)
        tracker2 = ValueTracker(0)

        sin_graph = axes.plot(lambda x: np.sin(x), color=BLUE, x_range=[-5, 5])

        def updatesin_graph(mob):
            mob.become(
                axes.plot(
                    lambda x: np.sin(tracker1.get_value() * x) + tracker2.get_value(),
                    color=BLUE,
                    x_range=[-5, 5],
                )
            )

        sin_graph.add_updater(updatesin_graph)

        lhs = [0, 0, 0, 0, 0, 0, 0]
        rhs = [0, 0, 0, 0, 0, 0, 0]
        eq = [0, 0, 0, 0, 0, 0, 0]
        leq = [0, 0, 0, 0, 0, 0, 0]
        req = [0, 0, 0, 0, 0, 0, 0]

        caption = [0, 0, 0, 0, 0, 0, 0]

        eq[0] = MathTex(r"=").scale(0.6).shift(UP * 2 + RIGHT * 1.2)
        for i in range(6):
            eq[i + 1] = MathTex(r"=").scale(0.6).next_to(eq[i], DOWN * 4)

        lhs[0] = MathTex(r"y", color=RED).scale(0.6).next_to(eq[0], LEFT)
        rhs[0] = (
            MathTex(r"\sin(\alpha\cdot x)+\beta", color=BLUE)
            .scale(0.6)
            .next_to(eq[0], RIGHT)
        )

        self.play(Write(title), Create(axes), Create(numberplane))  # Create(fun))
        self.wait(5)

        self.play(Write(lhs[0]))
        self.wait(2)
        self.play(Write(eq[0]), Write(rhs[0]))

        self.wait(5)
        self.play(Create(sin_graph))
        self.wait(2)
        self.play(tracker1.animate.set_value(3), run_time=5)
        self.play(tracker1.animate.set_value(0.01), run_time=5)
        self.play(tracker1.animate.set_value(1), run_time=3)
        self.wait(5)

        self.play(tracker2.animate.set_value(3), run_time=5)
        self.play(tracker2.animate.set_value(-3), run_time=5)
        self.play(tracker2.animate.set_value(0), run_time=3)
        self.wait(5)
        self.play(sin_graph.animate.set_color(ORANGE))

        self.wait(5)


class ShowFunc(ThreeDScene):
    def func1(self, u, v):
        return np.array([u, v, 24 * u**2 + 4 * v**2 - u * v**2])

    def func2(self, u, v):
        return np.array([u, 2 * u - 1, v])

    def construct(self):
        # 3d stuff

        title = MathTex(r"f(x,y)=24x^2+4y^2-xy^2.", color=TEAL).scale(0.6)
        title.to_edge(DOWN)

        axes = ThreeDAxes(
            x_range=[-2, 6, 5],
            y_range=[-20, 20, 5],
            z_range=[-50, 1500, 200],
            x_length=5.0,
            y_length=5.0,
            z_length=4.0,
        ).shift(DOWN)
        axes_labels = axes.get_axis_labels()
        # vecv = Arrow(ORIGIN, [1/2.5, 3/2.5, 0], buff=0, color=RED, stroke_width=1)

        P1 = Dot([axes.coords_to_point(0, 0, 0)]).scale(1.5)
        label1 = MathTex(r"(0,0,0)").scale(0.8).next_to(P1)

        P2 = Dot([axes.coords_to_point(4, -8 * 3 ** (1 / 2), 384)], color=ORANGE).scale(
            1.5
        )
        label2 = MathTex(r"(4,-8\sqrt{3},384)").scale(0.8).next_to(P2)

        P3 = Dot([axes.coords_to_point(4, 8 * 3 ** (1 / 2), 384)], color=ORANGE).scale(
            1.5
        )
        label3 = MathTex(r"(4,8\sqrt{3},384)").scale(0.8).next_to(P3)

        surface = Surface(
            lambda u, v: axes.c2p(*self.func1(u, v)),
            u_range=[-2, 6],
            v_range=[-20, 20],
            resolution=8,
        )
        surface.set_fill_by_checkerboard(BLUE, BLUE, opacity=0.5)

        # self.add_fixed_in_frame_mobjects(title)

        self.add_fixed_in_frame_mobjects(title)
        self.set_camera_orientation(theta=280 * DEGREES, phi=60 * DEGREES, zoom=1)
        self.add(axes, axes_labels)

        self.play(Create(surface))
        self.wait(3)
        self.play(
            Create(P1),
            Create(P2),
            Create(P3),
            Write(label1),
            Write(label2),
            Write(label3),
        )
        # self.wait(5)
        # self.play(Create(L))
        self.wait(2)
        self.begin_ambient_camera_rotation(rate=0.8)
        self.wait(16)
        self.stop_ambient_camera_rotation()
        self.wait(1)
        self.move_camera(theta=280 * DEGREES, phi=60 * DEGREES, zoom=1)

        self.wait(5)
```

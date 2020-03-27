---
layout: post
title: Exercises from "Fundamentals of Astrodynamics" Part 3
categories: [Orbital Mechanics, Fundamentals of Astrodynamics]
tags: [period, apogee, perigee, semi-major axis, ]
---

Again, we're back in “Fundamentals of Astrodynamics” by Bate, Mueller, and White,
continuing with the first problem set.

**Exercise 1.3** An Earth satellite is observed to have a height of perigee of
100 NM and a height of apogee of 600 NM.  Find the period of the orbit.

**Solution**:

Unlike other questions in the book, this one does not come with an answer to
check your work against.  Thus, it is important to ask yourself: does my answer
make sense?  When I first solved this problem, I took 100 NM and 600 NM to be
the radius of perigee and apogee, respectively, not giving much thought to how
this would be an extremely small orbit "inside" the Earth.  The answer of course
instantly made me realize my error and I then recomputed assuming the height to
be that of the satellite above the Earth's mean equatorial radius of 3443.923 NM
as given in Appendix A.  As you'll see below, the solution given this assumption
is much more realistic, especially knowing the period of common low Earth orbit
objects such as the International Space Station.

To begin, the equation for the period, $$T$$, of an elliptical orbit is:

$$

T = \frac{2\pi}{\sqrt{\mu}}a^{3/2},

$$

where $$a$$ is the semi-major axis and $$\mu$$ is the gravitational parameter,  
1.40765x10<sup>16</sup> ft<sup>3</sup>s<sup>-2</sup> for Earth.  Recall that
$$a$$ can simply be calculated as:

$$

a = \frac{r_a + r_p}{2},

$$

where $$r_a$$ is the radius of apogee and $$r_p$$ is the radius of perigee.
These two radii can be found by adding the Earth's mean equatorial radius,
$$r_\oplus$$, and the height of the satellite at the two respective positions:

$$

\displaylines{
  r_a = r_\oplus + r_{ha} \\
  r_p = r_\oplus + r_{hp},
}

$$

where $$r_{ha}$$ is the height of apogee and $$r_{hp}$$ is the height of
perigee. Substituting these into our equation for $$a$$ yields:

$$

\begin{align*}
a &= \frac{r_\oplus + r_{ha} + r_\oplus + r_{hp}}{2} \\
  &= r_\oplus + \frac{r_{ha} + r_{hp}}{2} \\
  &= 3793.923 \: \textrm{NM}.
\end{align*}

$$

Plugging in our knowns into our equation for the orbital period yields the
solution:

$$

\begin{align*}
T &= \frac{2\pi}{\sqrt{\mu}}a^{3/2} \\
  &= 2\pi\frac{\left( 3793.923*6076.12 \right)^{3/2}}{\sqrt{1.40765\times10^{16}}} \\
  &= 5861.447 \: \textrm{s} \\
  &= 97.69 \: \textrm{min}. \blacksquare
\end{align*}

$$

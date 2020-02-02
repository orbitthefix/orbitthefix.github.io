---
layout: post
title: Exercises from "Fundamentals of Astrodynamics" Part 5
categories: [Orbital Mechanics, Fundamentals of Astrodynamics]
tags: [eccentricity, true anomaly, semi-latus rectum, apoapsis,
trajectory equation ]
---

Moving on to the next problem in chapter 1 of “Fundamentals of
Astrodynamics” by Bate, Mueller, and White, we arrive at a simple proof.

**Exercise 1.7** Prove that $$r_{apoapsis}=a(1 + e)$$.

**Solution**:

By inspection of the figure in my previous post:

$$

r(\pi) = r_{apoapsis}.

$$

In simple language, apoapsis (i.e. maximum radial distance) happens 180
<sup>O<\sup>, or $$\pi$$ radians from periapsis (i.e. minimum radial distance).
To show that $$r_{apoapsis}=a(1 + e)$$, we'll revisit equation 1.5-4 from the
book, a form of the trajectory equation called the polar equation of a conic
section:

$$

r(\nu) = \frac{p}{1+e\cos{\nu}}, \\

$$

where $$r$$, is the radial distance from the focus as a function of the true
anomaly, $$\nu$$, the semi-latus rectum, $$p$$, and the eccentricity, $$e$$.  We
can substitute equation 1.5-6 for the semi-latus rectum and complete the proof:

$$

p = a \left (1 - e^2 \right ) \\
\therefore r(\nu) = \frac{a \left (1 - e^2 \right )}{1+e\cos{\nu}} \\
\begin{align*}
r(\pi) &= \frac{a \left (1 - e^2 \right )}{1 - e} \\
       &= \frac{a(1 + e)(1 - e)}{1 - e} \\
       &= \frac{a(1 + e) \cancel{(1 - e)}}{\cancel{1 - e}} \\
       &= a(1 + e) \\
\end{align*}
\because r_{apoapsis}=r(\nu) \\
r_{apoapsis}=a(1 + e).
\blacksquare

$$

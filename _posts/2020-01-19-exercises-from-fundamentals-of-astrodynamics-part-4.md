---
layout: post
title: Exercises from "Fundamentals of Astrodynamics" Part 4
categories: [Orbital Mechanics, Fundamentals of Astrodynamics]
tags: [velocity, specific mechanical energy, ]
---

Continuing with “Fundamentals of Astrodynamics” by Bate, Mueller, and White,
but skipping around a little, it's time for an easy one!

**Exercise 1.6** Find an equation for the velocity of a satellite as a function
of total specific mechanical energy and distance from the center of the earth.

**Solution**:

Skipping the derivation for now (I'll save that for another post) the equation
for specific mechanical energy, $$\mathcal{E}$$, is:

$$

\mathcal{E} = \frac{v^2}{2} - \frac{\mu}{r},

$$

where $$v$$ is the velocity, $$\mu$$ is the gravitational parameter,
1.40765x10<sup>16</sup> ft<sup>3</sup>s<sup>-2</sup> for Earth, and $$r$$ is the
radial distance from the center of the earth to the satellite.  Simply
rearranging for $$v$$ yields the desired equation:

$$

\displaylines{
  \frac{v^2}{2} = \mathcal{E} + \frac{\mu}{r} \\
  \therefore v = \sqrt{2 \left ( \mathcal{E} + \frac{\mu}{r} \right )}.
  \blacksquare
}

$$

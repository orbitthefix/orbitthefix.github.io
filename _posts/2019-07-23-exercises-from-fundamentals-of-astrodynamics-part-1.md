---
layout: post
title: Exercises from "Fundamentals of Astrodynamics" Part 1
categories: [Orbital Mechanics]
---

Over the coming months, years, decades, no one really knows, I will be working
through the exercises from "Fundamentals of Astrodynamics" by Bate, Mueller, and
White.  The intent is to not only provide myself with a refresher, but to
provide a resource for enterprising students.

$$

\renewcommand{\vec}[1]{\mathbf{#1}}

$$

**Exercise 1.1** The position, $$ \vec{r} $$, and velocity, $$ \vec{v} $$, of a
satellite at a given instant in canonical units: Distance Units (DU) and
Distance Units per Time Unit (TU), respectively, are described by

$$

\vec{r} = 2\vec{I} + 2\vec{J} + 2\vec{K} \quad \textrm{DU} \\
\vec{v} = -.4\vec{I} + .2\vec{J} + .4\vec{K} \quad \textrm{TU}

$$

Find the specific angular momentum, $$ \vec{h} $$, and specific mechanical
energy, $$ \mathcal{E} $$, of the system.

**Solution**:

Equation for specific angular momentum:

$$

\vec{h} = \vec{r} \times \vec{v} \\


$$

An easy way to set up the crossproduct is using [Sarrus' scheme][sarrus]:

![sarrus' scheme]({{ "public/posts/2019-07-23-sarrus.png" | relative_url }}){: .center-image }

This yields:

$$

2 \cdot 0.4 \cdot \vec{I} - 2 \cdot 0.2 \cdot \vec{I} = 0.4 \cdot \vec{I} \\
2 \cdot (-0.4) \cdot \vec{J} - 2 \cdot 0.4 \cdot \vec{J} = -1.6 \cdot \vec{J} \\
2 \cdot 0.2 \cdot \vec{K} - (-0.4) \cdot 0.2 \cdot \vec{K} = 1.2 \cdot \vec{K} \\

\\~\\

\therefore \vec{h} = 0.4 \vec{I} - 1.6 \vec{J} + 1.2 \vec{K} \quad \frac{\textrm{DU}^2}{\textrm{TU}}

$$

Equation for specific mechanical energy:

$$

\mathcal{E} = \frac{v^2}{2}  - \frac{\mu}{r} \\

v^2 = |\vec{v}|^{2} \\
\therefore v^2 = (-0.4)^2 + 0.2^2 + 0.4^2 = 0.36 \quad \frac{\textrm{DU}^2}{\textrm{TU}^2} \\
r = |\vec{r}| = \left( 2^2 + 2^2 +2^2 \right)^{\frac{1}{2}} = 12^{\frac{1}{2}} \quad \textrm{DU} \\

$$

Since we're using canonical units, let $$\mu = 1$$:

$$

\therefore \mathcal{E} = \frac{0.36}{2}  - \frac{1}{12^{\frac{1}{2}}} = -0.1087 \quad \frac{\textrm{DU}^2}{\textrm{TU}^2}

$$

[sarrus]:https://en.wikipedia.org/wiki/Rule_of_Sarrus

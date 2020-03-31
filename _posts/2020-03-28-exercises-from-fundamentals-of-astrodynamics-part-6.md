---
layout: post
title: Exercises from "Fundamentals of Astrodynamics" Part 6
categories: [Orbital Mechanics, Fundamentals of Astrodynamics]
tags: [eccentricity, periapsis, apoapsis, velocity, specific mechanical energy,
trajectory equation ]
---

In this post, we'll focus on a multi-part problem in chapter 1 of “Fundamentals
of Astrodynamics” by Bate, Mueller, and White, that introduces some basics of
orbit determination, namely eccentricity.

$$

\renewcommand{\vec}[1]{\mathbf{#1}}

$$

**Exercise 1.8** Identify each of the following trajectories as either circular,
elliptical, hyperbolic, or parabolic:

a.

$$ \displaylines{
   r = 3 \quad \textrm{DU} \\
   v = 1.5 \quad \textrm{DU/TU}
  }
$$

b.

$$ \displaylines{
   r_{perigee} = 1.5 \quad \textrm{DU} \\
   p = 3 \quad \textrm{DU}
  }
$$

c.

$$ \displaylines{
   \mathcal{E} = -1/3 \quad \textrm{DU}^2/\textrm{TU}^2 \\
   p = 1.5 \quad \textrm{DU/TU}
  }
$$

d.

$$ \displaylines{
    \vec{r} = \vec{J} + 0.2\vec{K} \\
    \vec{v} = 0.9\vec{I} + 0.123\vec{K}
   }
$$

e.

$$ \displaylines{
    \vec{r} = 1.01\vec{K} \\
    \vec{v} = \vec{I} + 1.4\vec{K}
   }
$$

**Solution**:

Our goal to determine the type of orbit for all of the following will be to find
an expression of eccentricity based on our knowns.  

a.

$$ \displaylines{
   r = 3 \quad \textrm{DU} \\
   v = 1.5 \quad \textrm{DU/TU}
  }
$$

Given a scalar position and velocity, $$r$$ and $$v$$, respectively, we seek to
equate these to eccentricity, $$e$$.  Unfortunately, to my knowledge an equation
does not exist only knowing these two scalar values to directly solve for $$e$$.
However, we can get close enough and use a reasonable assumption to make the
leap to declaring what type of orbit it is.  Recall the equation for specific
mechanical energy, $$\mathcal{E}$$:

$$
\mathcal{E} = \frac{v^2}{2} - \frac{\mu}{r},
$$

where $$v$$ is velocity, $$r$$ is position, and  $$\mu$$ is the gravitational
parameter (for our purposes equal to unity due to working in canonical units).  
Solving this yields a positive result:

$$
\begin{align*}

\mathcal{E} &= \frac{1.5^2}{2} - \frac{1}{3} \\
            &= \frac{10}{24} \quad \textrm{DU}^2/\textrm{TU}^2.  

\end{align*}
$$

Using this result along with equation 1.6-4 from the book allows us to determine
the type of orbit:

$$

\begin{align*}
e &= \sqrt{1 + \frac{2\mathcal{E}h^2}{\mu}} \\
  &= \sqrt{1 + \frac{2 \left( 10/24 \right)h^2}{1}},
\end{align*}

$$

where $$h$$ is specific angular momentum.  But what is $$h$$?  We can't solve
for an exact value for $$h$$ without knowing the flight path angle, $$\phi$$,
because $$r$$ and $$v$$ are scalars.  But that doesn't matter.  We don't care
what $$h$$ is as long as it's not zero, which would only be the case for a
degenerate conic (essentially a point in space or straight line), because $$h$$
is squared in the above equation.  The leap in insight here is to see that
because one is being added to a positive number greater than zero under the
square-root, $$e$$ must be greater than one and therefore the orbit is a
hyperbola.

b.

$$ \displaylines{
   r_{perigee} = 1.5 \quad \textrm{DU} \\
   p = 3 \quad \textrm{DU}
  }
$$

We can solve for $$e$$ using the polar equation of a conic section knowing the
semi-latus rectum, $$p$$, and that the periapsis distance, $$r_p$$, occurs when
the true anomaly, $$\nu$$, is zero as follows:

$$ \displaylines{
    r = \frac{p}{1+e\cos{\nu}} \\
    \because r(0) = r_p \\
    r_p = \frac{p}{1+e\cos{0}} = \frac{p}{1+e} \\
    \therefore e = \frac{p}{r_p}-1 = \frac{3}{3/2}-1 = 1.
  }
$$

The resultant eccentricity being unity means the orbit is a parabola.

c.

$$ \displaylines{
   \mathcal{E} = -1/3 \quad \textrm{DU}^2/\textrm{TU}^2 \\
   p = 1.5 \quad \textrm{DU/TU}
  }
$$

Given $$\mathcal{E}$$ and $$p$$, we can use equation 1.6-4 from the text with a
simple substitution for the specific angular momentum, $$h$$, and solve directly
for $$e$$:

$$ \displaylines{
    e = \sqrt{1 + \frac{2\mathcal{E}h^2}{\mu^2}} \\
    \because h = p\mu \\
    e = \sqrt{1 + \frac{2\mathcal{E}p}{\mu}} \\
    \therefore e = \sqrt{1 + \frac{2(-1/3)(3/2)}{1}} = 0.
  }
$$

The resultant eccentricity being zero means the orbit is a circle.

d.

$$ \displaylines{
    \vec{r} = \vec{J} + 0.2\vec{K} \quad \textrm{DU} \\
    \vec{v} = 0.9\vec{I} + 0.123\vec{K} \quad \textrm{DU/TU}
   }
$$

Only being given vectors for position, $$\vec{r}$$, and velocity, $$\vec{v}$$,
we must find both $$h$$ and $$\mathcal{E}$$ before we can solve for $$e$$. The
specific angular momentum can easily be solved for using [Sarrus'scheme][sarrus]
to find the cross-product:

$$

\vec{h} = \vec{r} \times \vec{v}

$$

![sarrus' scheme]({{ "public/posts/2020-03-28-sarrus.png" | relative_url }}){: .center-image }

$$

\begin{align*}
\therefore \vec{h} &= 0.123\vec{I} + 0.9 \cdot 0.2 \vec{J} - 0.9 \vec{K} \\
                   &= 0.123\vec{I} + 0.18 \vec{J} - 0.9 \vec{K} \quad \textrm{DU}^2/\textrm{TU}.
\end{align*}

$$

The specific mechanical energy is a function of the scalars velocity and
position:

$$ \displaylines{
r = \sqrt{1^2+0.2^2} = \sqrt{1.04} \quad \textrm{DU} \\
v^2 = 0.9^2 + 0.123^2
}
$$

$$
\begin{align*}
\mathcal{E} &= \frac{v^2}{2}-\frac{\mu}{r} \\
            &= \frac{\left(0.9^2 + 0.123^2\right)}{2}-\frac{1}{\sqrt{1.04}} \\
            &= -0.568 \quad \textrm{DU}^2/\textrm{TU}^2.
\end{align*}          
$$

We can now solve for the eccentricity using equation 1.6-4 from the text:

$$
\begin{align*}
e &= \sqrt{1 + \frac{2\mathcal{E}h^2}{\mu^2}} \\
  &= \sqrt{1 + \frac{2(-0.568)(0.123^2 + 0.18^2 + (-0.9)^2)}{1^2}} \\
  &= 0.159.
\end{align*}
$$

The resultant eccentricity being less than one means the orbit is an ellipse.

e.

$$ \displaylines{
    \vec{r} = 1.01\vec{K} \quad \textrm{DU} \\
    \vec{v} = \vec{I} + 1.4\vec{K} \quad \textrm{DU/TU}
   }
$$

This final problem can be solved in the exact same way as the previous. For
brevity, I'll skip any explanation and just show steps:

$$

\begin{align*}
\vec{h} &= \vec{r} \times \vec{v} \\
        &= 0\vec{I} + 1.01 \vec{J} + 0 \vec{K} \\
        &= 1.01 \vec{J} \quad \textrm{DU}^2/\textrm{TU}
\end{align*}

$$

$$
\displaylines{
r = \sqrt{1.01^2} = 1.01 \quad \textrm{DU} \\
v^2 = 1^2 + 1.4^2 = 2.96 \quad (\textrm{DU/TU})^2
}

\begin{align*}
\mathcal{E} &= \frac{v^2}{2}-\frac{\mu}{r} \\
            &= \frac{2.96}{2}-\frac{1}{1.01} \\
            $= 0.49 \quad \textrm{DU}^2/\textrm{TU}^2.
\end{align*}          
$$

$$
\begin{align*}
e &= \sqrt{1 + \frac{2\mathcal{E}h^2}{\mu^2}} \\
  &= \sqrt{1 + \frac{2(0.49)(1.01^2)}{1^2}} \\
  &= 1.41.
\end{align*}
$$

The resultant eccentricity being greater than one means the orbit is a
hyperbola. $$\blacksquare$$



[sarrus]:https://en.wikipedia.org/wiki/Rule_of_Sarrus

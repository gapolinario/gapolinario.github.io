---
layout: post
title:  "Burgers Equation I: The Integrating Factor Method"
date:   2018-08-08 10:00:00 -0300
categories: math, physics
---

This is the first post on a series about the Burgers equation,
I am going to discuss analytical and numerical techniques for its numerical
solution. These tools are certainly useful for other
heat-type partial differential equations.

The Burgers equation is prominent in several areas of research, can be
used to model one-dimensional shocks in water, gases and even traffic.
It was proposed as a one-dimensional version of Navier-Stokes
equation by Harry Bateman in 1915 and studied by Johannes Martinus Burgers in 1948.
The equation describes how the field $u(x,t)$ evolves in time

$$ \frac{d u}{dt} +  u \frac{d u}{dx} = \nu \frac{d^2 u}{dx^2} $$

The parameter $\nu$ is the diffusion coefficient, or kinematic viscosity.

We can take a Fourier transform in the $x$ direction,
our notation is

$$\tilde u (k,t) = \mathcal{F}_x \big\{ u(x,t) \big\}$$

and we might suppress the arguments of $u$ and $\tilde u$, for they are clear from the context.
Our Fourier transformed equation is

$$ \frac{d}{dt} \tilde u + \nu k^2 \tilde u = \tilde F $$

Where 

$$\tilde F(k,t) = - \mathcal{F}_x \left\{ u \frac{d u}{dx} \right\}$$


Now I am going to introduce the integrating factor method,
which is commonly used in numerical simulations of Burgers and similar PDEs.
Multiply both sides by $ e^{\nu k^2 t}$ and define

$$\tilde U(k,t) = e^{\nu k^2 t} \ \tilde u(k,t) $$

well, its derivative with respect to $t$ is

$$\frac{d}{dt} \tilde U = e^{\nu k^2 t} \frac{d}{dt} \tilde u + \nu k^2 e^{\nu k^2 t} \tilde u $$

And our original equation can be rewritten as

$$ \frac{d}{dt} \tilde U = e^{\nu k^2 t} \tilde F $$

The simplest way to solve this equation numerically is using [Euler's method][euler].

$$ \frac{1}{\Delta t} \left(
e^{\nu k^2 (t_n + \Delta t)} \tilde u^{n+1}_k - e^{\nu k^2 t_n} \tilde u^{n}_k \right)
 = e^{\nu k^2 t_n} \tilde F^n_k $$
 
$$ \tilde u^{n+1}_k = (\tilde u^{n}_k + \Delta t \ \tilde F^n_k ) e^{-\nu k^2 \delta t} $$


[euler]: https://en.wikipedia.org/wiki/Euler_method
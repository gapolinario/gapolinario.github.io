---
layout: post
title:  "Generating Gaussian Correlated Noise"
date:   2024-04-21 12:00:00 -0300
categories: physics
---

How can you generate gaussian random noise with a given correlation length?

Say you want to generate random noise but correlated with
a certain known correlation function, how can you do that?

(this kind of noise is defined only by its
mean zero and two point correlation function, what
does this mean? this is still Gaussian, but correlated?)

Well, we have the two point auto correlation of a certain
random field

A certain Gaussian noise with zero mean and specified
correlation function is defined by

$$ \langle \eta(x) \rangle = 0 $$

$$
 \langle \eta(x+\delta x) \eta(x) \rangle = \chi (\delta x)
$$

why Gaussian? because it is defined explicitly
by its mean and correlation function

and $\chi$ is an arbitrary function (with what properties?
decaying at infinity?)

If you generate a realization of this random field, you can calculate
its autocorrelation, explicitly, this is

I mean, this is the sample autocorrelation,
and the index would be different realizations, then strictly
this is a sum, not an integral

\begin{equation}
 \langle \int_0^L dx \ \eta_i(x+\delta x) \eta_i(x) \rangle_R
\end{equation}

where there were $R$ realizations, indexed by $i = 1, 2, \ldots, R$

where $L$ is the size of the system. One assumes this was defined
with periodic boundary conditions, so that $x+\delta x$ never
leaves the boundaries of the system, $[0,L]$.

Then we can fourier transform the eta fields

$$
  \langle \eta(x+\delta x) \eta(x) \rangle =
  \langle \int dx \
  \frac{1}{2 \pi} \int dk \ \tilde \eta(k) \ e^{i k (x+\delta x)}
  \frac{1}{2 \pi} \int dk' \ \tilde \eta(k') \ e^{i k' x} \rangle_R
$$

$$
  \langle \frac{1}{2 \pi}
  \int dk \ \tilde \eta(k) \ e^{i k \delta x}
  \int dk' \ \tilde \eta(k') \delta(k+k') \rangle_R
$$

$$
  \langle \frac{1}{2 \pi}
  \int dk \ \tilde \eta(k) \tilde \eta(-k) \ e^{i k \delta x} \rangle_R
$$

Plus, we have real noise, this means, for its Fourier transform,
that

$$
\tilde \eta^*(k) = \tilde \eta(-k)
$$

So that

$$
  \chi (\delta x) = \frac{1}{2 \pi} \int dk \ \tilde \chi(k) \ e^{i k \delta x}
  =
  \frac{1}{2 \pi}
  \int dk \ \langle | \tilde \eta(k) |^2 \rangle_R \ e^{i k \delta x}
$$

This means that

\begin{equation}
 \tilde \chi(k) = \langle | \tilde \eta(k) |^2 \rangle_R
\end{equation}

So that we have the standard deviation for the fourier transformed
$|\tilde \eta(k)|$ field, together with knowledge of its
average, which is zero, one simply has to sample $\tilde \eta(k)$
with a normal distribution of zero mean and
$\tilde \chi(k)$ standard deviation, and the two point autocorrelation
of  $\langle \eta(x+\delta x) \eta(x) \rangle$
is going to satisfy $\chi(x)$, as needed.

s
---
layout: post
title:  "High Dimensional Fractional Gaussian Fields"
date:   2021-07-02 18:00:00 +0200
categories: physics
---

% opening paragraph

In the last post, I showed some numerical simulations. I will focus on analytical results for the statistical observables in arbitrary dimensions. For d=1,2,3, these values were used on the dashed lines in the plots.

A fractional Gaussian field is defined in $d$-dimensions as

$$
u_H(x) = \int_{\mathbb{R}^d} e^{2\pi i k \cdot x} \frac{1}{\lvert k \lvert^{H+d/2}_{1/L}} \widehat{dW}(k) \ ,
$$

where $\lvert k \lvert_{1/L}$ denotes a regularized norm over small wavelengths
$k$, meaning that $\lvert k \lvert_{1/L} \approx 1/L$ for small $k$ and $\lvert k \lvert_{1/L} \approx \lvert k \lvert$ for large $k$. One possible choice for this regularization is $\lvert k \lvert_{1/L} = \sqrt{k \cdot k + 1/L^2}$. The increment of a white noise field is denoted by $dW$ and its Fourier transform by $\widehat{dW}$.

The statistics of this random field is Gaussian, as is clear from its name and definition, since we have an integral over Gaussian random variables (white noise). To characterize it, we can look at the power spectrum,

$$
E(k) = \int d\Omega \, k^{d-1} \mathbb{E}\lvert \hat u_H \lvert^2 \ ,
$$

First, we have
$$ \mathbb{E}\lvert \hat u_H \lvert^2 = |k|^{-2H-d} $$
obtained from the correlation function of white noise
$$ \mathbb{E}W(x_1)W(x_2) = \delta^d(x_1-x_2) $$
then
E(k) \sim \Omega_d \, k^{-2H-1} ,

at large k, where $\Omega_d$ is the surface area in $d$ dimensions.
This is the correct power law decay

Variance is

$$ \mathbb{E}|u_H|^2 = \int_{\mathbb{R}^d} dk \frac{1}{\lvert k \lvert^{2H+d}_{1/L}} $$

in 1D, this is

$$ \frac{\sqrt{\pi} \Gamma(H)}{\Gamma(H+1/2)} L^{2H} $$

in 2D

$$ \frac{\pi}{H} L^{2H} $$

and in arbitrary dimension

$$ \mathbb{E}|u_H|^2 = \Omega_d \int_{\mathbb{R}^+} dk \frac{k^{d-1}}{\lvert k \lvert^{2H+d}_{1/L}}
= \frac{\pi^{d/2} \Gamma(H)}{\Gamma(H+d/2)} L^{2H} $$

and the second order structure function ($\mathbb{E} \lvert \delta_{\ell} u_H \lvert^2$), where the increment is defined as

$$
\delta_{\ell} u_H(x) = u_H(x+\ell e_i) - u_H(x)
$$

for some unit vector $e_i$

$$
\mathbb{E} \lvert \delta_{\ell} u_H \lvert^2 =
\int_{\mathbb{R}^d} dk \frac{\lvert e^{2\pi i \ell k \cdot e_i}-1 \lvert}{\lvert k \lvert_{1/L}^{2H+d}}
$$

with $\lvert e^{2\pi i \ell k \cdot e_i}-1 \lvert = 2(1-\cos(2\pi \ell k \cdot e_i))$

the following integrals are calculated after taking the $L \to 0$ limit, since we are interested in the regime $\ell \to 0$ as well

Still need to show how the $L$ disappears and the $\ell$ disappears from all expressions below.

in 1D

$$ \frac{(2\pi)^{1+2H}}{\sin(\pi H) \Gamma(1+2H)} $$

in 2D we can choose the system of coordinates such that

$$
k \cdot e_i = k \cos \theta
$$

The integral in $\theta$ is

$$
\int_0^{2\pi} d\theta ( 1-\cos(2 \pi k \cos \theta ) ) = 2 \pi (1- J_0(2\pi \ell))
$$

where $J_0$ is a Bessel function

then we need

$$ 4 \pi \int_{\mathbb{R}^+} dk (1-J_0(2\pi k)) k^{-2H-1} = \frac{2 \pi^{2+2H}}{\sin(\pi H) \Gamma^2(1+H)} $$

The 3D case is interesting because it can be done both with n-dimensional coordinates or
with standard spherical coordinates and both results match

With standard spherical coordinates, we have to calculate

$$
\int_0^{\pi} d\theta \sin \theta  \left( 1-\cos(2 \pi k \cos \theta ) \right) = 2 - \frac{\sin(2\pi k)}{\pi k}
$$

and then

$$
2 \int_{\mathbb{R}^+} dk \left( 2 - \frac{\sin(2\pi k)}{\pi k} \right) k^{-2H-1} = \frac{2 (2\pi)^{2H}}{\sin(\pi H) \Gamma(2+2H)}
$$

we still have to multiply by $2\pi$ after all this

in arbitrary dimensions, we have one angle from 0 to $2\pi$ and $d-2$ angles from 0 to $\pi$
and we can choose them in a way that
$k \cdot e_i = k \cos phi_1$ where $\phi_1$ is one of the angles from 0 to $\pi$.

in this way, the structure function is

$$
2 \int_{\mathbb{R}^+} dk \, k^{d-1} \int_{0}^{\pi} d\phi_1 \, \sin^{d-2}(\phi_1) \ldots
\int_{0}^{\pi} d\phi_{d-2} \, \sin(\phi_{d-2}) \int_{0}^{2 \pi} d\phi_{d-1}
( 1-\cos(2 \pi k \cos \phi_1 ) ) k^{-2H-1}
$$

the integral over $\phi_1$ is

$$
\frac{\sqrt{\pi}\Gamma(d/2-1/2)}{\Gamma(d/2)} (1- {}_0 F_1(d/2,-\pi^2 k^2))
$$

and twice the integral over $k$ is

$$
I_1 = \frac{\pi^{2H+3/2} \Gamma(d/2-1/2)}{\Gamma(1+H)\Gamma(H+d/2)}
$$

the remaining integrals, of the form

$$
I_n = \int_{0}^{\pi} d\phi \, \sin^n(\phi) = \frac{\sqrt{\pi}\Gamma(n/2+1/2)}{\Gamma(1+n/2)}
$$

and we have to multiply all that by $2\pi$ in the end (the last angular integral)

for $d=3$, we recover the same result

and in arbitrary dimension we have

$$
2\pi I_1 \ldots I_{d-2}
$$

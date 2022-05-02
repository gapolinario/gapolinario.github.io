---
layout: post
title:  "High Dimensional Fractional Gaussian Fields"
date:   2022-05-02 12:00:00 +0200
categories: math
---

In this post we'll look at the statistical properties of fractional Gaussian fields in arbitrary dimensions.

We denote vectors in real space by $x$ or $y$ and vectors in Fourier space by $k$ or $k'$. Their absolute values are indicated as $|x|$ and $|k|$. With this notation, a fractional Gaussian field in $d$-dimensions is defined as
$$
u_H(x) = \int_{\mathbb{R}^d} e^{2\pi i k \cdot x} \frac{1}{\lvert k \lvert^{H+d/2}_{1/L}} \widehat{dW}(k) \ ,
$$

where $\lvert k \lvert_{1/L}$ denotes a regularized norm over small wavelengths $k$, meaning that $\lvert k \lvert_{1/L} \approx 1/L$ for small $k$ and $\lvert k \lvert_{1/L} \approx \lvert k \lvert$ for large $k$. One possible choice for this regularization is $\lvert k \lvert_{1/L} = \sqrt{k \cdot k + 1/L^2}$. The increment of a complex Gaussian white noise field is denoted by $dW$ and its Fourier transform by $\widehat{dW}$. All calculations below follow from the statistical properties of this complex white noise: Its mean is zero and its correlation functions are
$$
\mathbb{E}[W(x) \overline{W(x')}] = \delta^{(d)}(x-x') \qquad \text{and} \qquad \mathbb{E}[W(x) \overline{W(x')}] = 0 ,
$$
where $\delta^{(d)}$ represents a Dirac delta function in $d$-dimensions and $\overline{W(x)}$ represents complex conjugation. The choice of correlation function above means that the real and imaginary components of $W(x)$ are independent.

The statistics of $u_H$ is Gaussian, since it is defined as an integral of Gaussian random variables. This is also hinted at by the name "fractional Gaussian field." To characterize this random field, we first note that its mean is zero, as it is easy to notice.

To characterize this random field, now we only need to look at its second order statistics, since it is Gaussian. This is what we do in the next paragraphs.

Let us now look at the **power spectrum** $E(k)$, defined as
$$
E(k) = \int_{\mathbb{R}^d} d^d(x-y) \, e^{-2\pi i k \cdot (x-y)} \mathbb{E}\left[ u_H(x) \overline{u_H(y)} \right] .
$$
With the definition of $u_H$, we can show that
$$
E(k) = \frac{1}{|k|_{1/L}^{2H+d}} ,
$$
which depends only on the absolute value of $k$. For this reason, we can define an angle-averaged spectrum, $E_{\Omega}(|k|)$, as
$$
E_{\Omega}(|k|) = \int d\Omega_d \, |k|^{d-1} E(k) ,
$$

where $d\Omega_d$ represents the $d$-dimensional spherical volume element. At large wavelengths, we obtain the asymptotic result
$$
E_{\Omega}(|k|) \underset{k \to \infty}{\sim} \Omega_d \, |k|^{-2H-1} .
$$
Another variable of interest is the **variance** of $u_H$, given by

$$
\mathbb{E}\left[ |u_H|^2 \right] = \int_{\mathbb{R}^d} d^dk \, E(k) = \int_{\mathbb{R}^+} d|k| \, E_{\Omega}(|k|) .
$$
This integral is finite for $H > 0$, and the result depends on the regularization chosen for $|k|$. If $u_H$ had not been regularized, the variance would be infinite. With the regularization chosen above, we have the explicit result

$$
\mathbb{E} \left[ |u_H|^2 \right] = \Omega_d \int_{\mathbb{R}^+} d|k| \frac{|k|^{d-1}}{\lvert k \lvert^{2H+d}_{1/L}}
= \frac{\Gamma(d/2) \, \Gamma(H)}{2 \, \Gamma(H+d/2)} L^{2H} .
$$

Another interesting observable is the **velocity gradient variance**, defined by
$$
\mathbb{E}\left[ |\nabla u_H|^2 \right] = 4 \pi^2 \int_{\mathbb{R}^d} d^dk \, |k|^2 E(k) = \int_{\mathbb{R}^+} d|k| \, |k|^2 E_{\Omega}(|k|) .
$$
This is not finite, though, it diverges for $H \leq 1$. This result is expected, since the velocity field $u_H$ is not differentiable for $H \leq 1$.

Ultimately, we'll look at the **statistics of increments**. Define an increment at distance $\ell$ of the velocity field as
$$
\delta_{\ell} u_H(x) = u_H(x+\ell e_i) - u_H(x)
$$

for some unit vector $e_i$. We'll calculate its variance, which is often called the **second order structure function**, given by

$$
\mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] =
\int_{\mathbb{R}^d} d^dk \frac{\lvert e^{2\pi i \ell k \cdot e_i}-1 \lvert^2}{\lvert k \lvert_{1/L}^{2H+d}} ,
$$

where we can also write $\lvert e^{2\pi i \ell k \cdot e_i}-1 \lvert^2 = 2(1-\cos(2\pi \ell k \cdot e_i))$.

Let us first take the limit $\ell \to 0$ to understand the asymptotic behavior of this quantity. With the change of variables $k \to k / \ell$, we obtain
$$
\mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] =
\ell^{-d} \int_{\mathbb{R}^d} d^dk \frac{\lvert e^{2\pi i k \cdot e_i}-1 \lvert^2}{\lvert k / \ell \lvert_{1/L}^{2H+d}} .
$$
In the limit of small increments, which is of interest to us,
$$
\lvert k / \ell \lvert_{1/L} = \frac{1}{\ell^2}\left( k^2 + \frac{\ell^2}{L^2} \right) \underset{\ell \to 0}{\sim} k^2 / \ell^2 .
$$
So we'll integrate
$$
\mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] \underset{\ell \to 0}{\sim}
\ell^{2H} \int_{\mathbb{R}^d} d^dk \frac{\lvert e^{2\pi i k \cdot e_i}-1 \lvert^2}{\lvert k \lvert^{2H+d}}
$$
This already shows us an asymptotic power-law growth exponent $2H$. Furthermore, this integral is finite for $ H < 1$, as we'll see.

In 1D

$$
\text{(1D)} \qquad \mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] \underset{\ell \to 0}{\sim} \frac{(2\pi)^{1+2H}}{\sin(\pi H) \Gamma(1+2H)} .
$$
In 2D we can choose the system of coordinates such that

$$
k \cdot e_i = k \cos \theta .
$$

The integral in $\theta$ is

$$
\int_0^{2\pi} d\theta \, ( 1-\cos(2 \pi |k| \cos \theta ) ) = 2 \pi (1- J_0(2 \pi |k|)) ,
$$

where $J_0$ is a Bessel function, and the full result it

$$
\text{(2D)} \qquad \mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] \underset{\ell \to 0}{\sim} 4 \pi \int_{\mathbb{R}^+} d|k| \left(1-J_0(2\pi |k|) \right) |k|^{-2H-1} = \frac{2 \pi^{2+2H}}{\sin(\pi H) \Gamma^2(1+H)}
$$
The 3D case is interesting because it can be done both with generalized spherical coordinates or with standard 3d spherical coordinates and both results match.

With 3D spherical coordinates, we have to calculate
$$
\int_{\mathbb{R}^3} d^3k \frac{\lvert e^{2\pi i k \cdot e_i}-1 \lvert^2}{\lvert k \lvert^{2H+d}}
= 2 \int_{0}^{2\pi} d\varphi \int_0^{\pi} \sin \theta \, d\theta \int_0^{\infty} |k|^2 d|k| \, \frac{1-\cos(2\pi |k| \cos \theta)}{\lvert k \lvert^{2H+3}}
$$
The integral in $\varphi$ is trivial. Then we can integrate in $\theta$,
$$
\int_0^{\pi} d\theta \sin \theta  \left( 1-\cos(2 \pi |k| \cos \theta ) \right) = 2 - \frac{\sin(2\pi |k|)}{\pi |k|} ,
$$

and finally

$$
2 \int_{\mathbb{R}^+} dk \left( 2 - \frac{\sin(2\pi |k|)}{\pi |k|} \right) |k|^{-2H-1} = \frac{2 (2\pi)^{2H}}{\sin(\pi H) \Gamma(2+2H)} .
$$

Multiplying all factors together, we obtain
$$
\text{(3D)} \qquad \mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] \underset{\ell \to 0}{\sim}
\ell^{2H} \frac{2 (2\pi)^{1+2H}}{\sin(\pi H) \Gamma(2+2H)}
$$
In arbitrary $d$-spherical coordinates, we have one angle from 0 to $2\pi$ and $d-2$ angles from 0 to $\pi$. They can be chosen in a way that $k \cdot e_i = k \cos \phi_1$ where $\phi_1$ is one of the angles from 0 to $\pi$. In this way, this structure function is
$$
2 \int_{\mathbb{R}^+} d|k| \, |k|^{d-1} \int_{0}^{\pi} d\phi_1 \, \sin^{d-2}(\phi_1) \ldots
\int_{0}^{\pi} d\phi_{d-2} \, \sin(\phi_{d-2}) \int_{0}^{2 \pi} d\phi_{d-1}
( 1-\cos(2 \pi |k| \cos \phi_1 ) ) |k|^{-2H-d}
$$

This integral is finite when the following integral is finite:
$$
\int_{\mathbb{R}^+} d|k| \, ( 1-\cos(2 \pi |k| \cos \phi_1 ) ) |k|^{-2H-1} .
$$
At infinity, integrability is obtained for $H > 0$, and at the origin, $H < 1$. Hence we have a finite result for $0 < H < 1$.

Now we can go back to the explicit computations. The integral over $\phi_1$ is
$$
f_1(|k|) = \int_{0}^{\pi} d\phi_1 \, \sin^{d-2} \phi_1 \left( 1-\cos(2 \pi |k| \cos \phi_1 ) \right) = \frac{\sqrt{\pi} \,\Gamma(d/2-1/2)}{\Gamma(d/2)} \left( 1- {}_0 F_1(d/2,-\pi^2 |k|^2) \right) .
$$

Then, the integral over $|k|$ is

$$
I_1 = 2 \int_{\mathbb{R}^+} d|k| \, \frac{f_1(|k|)}{|k|^{2H+1}} = \frac{\pi^{2H+3/2} \, \Gamma(d/2-1/2)}{\Gamma(1+H)\Gamma(H+d/2)} .
$$

The integral $\phi_{d-1}$ is simply $2\pi$. The remaining integrals are of the form

$$
I_n = \int_{0}^{\pi} d\phi \, \sin^{d-n-1} \phi = \frac{\sqrt{\pi} \,\Gamma\left(\frac{d-n}{2}\right)}{\Gamma\left(\frac{1}{2}(d-n+1)\right)}, \qquad \text{for $2 \leq n \leq d-2$}.
$$

This means that, in $d$ dimensions,
$$
\text{(dD)} \qquad \mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] \underset{\ell \to 0}{\sim}
\ell^{2H} \, 2 \pi \, I_1 \cdots I_{d-2}
$$
In three dimensions, this result is reduced to
$$
\text{(3D)} \qquad \mathbb{E} \left[ \lvert \delta_{\ell} u_H \lvert^2 \right] \underset{\ell \to 0}{\sim}
\ell^{2H} \, 2 \pi \, I_1 = \ell^{2H} \frac{2 (2\pi)^{1+2H}}{\sin(\pi H) \Gamma(2+2H)} ,
$$
as in our previous result.

An accompanying Mathematica notebook to this post is available on [Github][Github].

[Github]: https://github.com/gapolinario/high-dim-fgf

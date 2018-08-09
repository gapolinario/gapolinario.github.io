---
layout: post
title:  "More Numerical Fourier Transforms"
date:   2018-08-09 14:00:00 -0200
categories: math
math: true
---

I recently did a [post][nfourier] on a numerical method to find an analytical Fourier Transform, here I am again to explore more the topic,
discussing other conventions for the Fourier transform and inverse transforms.

Following the [MathWorld][mathworld] notation for the Fourier transforms, we write it as

$$
    \mathcal{F}_t[f(t)](\omega) = \tilde f(\omega) = \sqrt{\frac{\lvert b \lvert}{(2 \pi)^{1-a}}} \int_{-\infty}^{\infty} dt \ f(t) \ e^{i b \omega t}
$$

where $a$ and $b$ are called Fourier parameters.
Different conventions correspond to a different choice of parameters.
In my last post, the parameters used were $a=1$ and $b=-1$, or $(1,-1)$,
a convention commonly used in physics and mathematics.
But the same method can be applied with a different convention,
this is what will finally allow us to obtain the inverse transform.

The discrete Fourier transform, with general parameters, is given by

$$
    \mathcal{F}[x_j]_k = X_k = \frac{1}{N^{(1-a)/2}} \sum_{j=0}^{N-1} x_j \ e^{2 \pi i b j k /N}
$$

The same approach followed on the last post can be used to
write a numerical approximation to the analytical
Fourier transform.

Again we define $t_j = t_0 + j \Delta t$ and $ \omega_k = 2 \pi k / N \Delta t $,
and following the same approach as before, we obtain

\begin{equation} \label{gen_fourier}
\tilde f(\omega_k) =
\sqrt{\frac{\lvert b \lvert}{(2 \pi)^{1-a}}} \Delta t \ e^{i b \omega_k t_0} \ N^{(1-a)/2} \ X_k
\end{equation}

When $a=1$ and $b=-1$, this reduces to the expression we obtained before.

The inverse transform corresponds
to the usual Fourier transform with the parameters $-a$ and $-b$,
this can be seen from the definition, since the inverse transform is

$$
    \mathcal{F}^{-1}_{\omega}[\tilde f(\omega)](t) = f(t) = \sqrt{\frac{\lvert b \lvert}{(2 \pi)^{1+a}}} \int_{-\infty}^{\infty} dt \ \tilde f(\omega) \ e^{- i b \omega t}
$$

With this substitution in Eq. $\eqref{gen_fourier}$,
and exchanging occurrences of $\omega$ and $t$, $X$ and $x$
(and optionally $j$ and $k$, which are mute sum variables),
we obtain an expression for the Inverse Fourier transform:

$$
f(t_j) =
\sqrt{\frac{\lvert b \lvert}{(2 \pi)^{1+a}}} \ \Delta \omega \ e^{- i b \omega_0 t_j} \ N^{(1+a)/2} \ x_j
$$

If the convention used is $(1,-1)$, this reduces to

$$
f(t_j) =
\frac{N}{2 \pi} \ \Delta \omega \ e^{- i\omega_0 t_j} \ x_j
$$

I applied this to the same function as in the previous post,
to verify that the inverse transform does work, and here is the result:

![Gate function after a transform and an inverse transform]({{ "/assets/inverse-nfourier.png" | absolute_url }})

The Mathematica code for these transforms is available on [Github][gist].

[nfourier]: {% post_url 2018-04-11-approximating-the-analytical-fourier-transform-with-the-discrete-fourier-transform %}
[mathworld]: http://mathworld.wolfram.com/FourierTransform.html
[gist]: https://gist.github.com/gapolinario/a0d46ee387a93de6f6a4395acb522a5c
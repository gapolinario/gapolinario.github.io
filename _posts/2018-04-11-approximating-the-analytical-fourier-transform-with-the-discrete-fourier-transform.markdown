---
layout: post
title:  "Approximating the analytical Fourier transform with the Discrete Fourier transform"
date:   2018-04-11 21:00:00 -0200
categories: math
math: true
---

We would like to use the Discrete Fourier transform as an approximation
to the analytical Fourier Transform

If you have a set of N points labeled $x_i$, where $i$ ranges from
0 to $N-1$,
its Fourier transform is defined as

$$    X_k = \sum_{j=0}^{N-1} x_j \ e^{-2 \pi i j k /N} $$

This is just multiplication of a matrix and a vector

$$    \begin{pmatrix}
    X_0 \\ X_1 \\ X_2 \\ \vdots \\ X_{N-1}
    \end{pmatrix}
    =
    \begin{pmatrix}
    1 & 1 & 1 & \ldots & 1 \\
    1 & e^{-2 \pi i/N} & e^{-4 \pi i/N} & \ldots & e^{-2 \pi i (N-1) /N} \\
    1 & e^{-4 \pi i/N} & e^{-8 \pi i/N} & \ldots & e^{-4 \pi i (N-1) /N} \\
    \vdots & \vdots & \vdots & \ddots & \vdots \\
    1 & e^{-2 \pi i (N-1) /N} & e^{-4 \pi i (N-1) /N} & \ldots & e^{-2 \pi i (N-1)(N-1) /N} \\
    \end{pmatrix}
    \begin{pmatrix}
    x_0 \\ x_1 \\ x_2 \\ \vdots \\ x_{N-1}
    \end{pmatrix}
$$

One could do this naive multiplication, but the number of operations grows as $\mathcal{O}(N^2)$.
Luckily, we have a much better algorithm for this, which is the Fast Fourier Transform,
running in $\mathcal{O}(N \log N)$.

Besides, if you have a continuous function $f(t)$, its Fourier transform is defined
similarly, as

$$
    \tilde f(\omega) = \int_{-\infty}^{\infty} dt \ f(t) e^{- i \omega t}
$$

Now, say $f(t)$ has a compact support,
this means that this function is null outside of an interval $[t_0,t_N]$.
We then sample this function on a discrete set of points, evenly spaced,
these points are

$$
    t_j = t_0 + j \Delta t
$$

where $\Delta t = (t_N - t_0)/N$ is the spacing between these points.
And each value $x_j$ corresponds to $f(t_j)$.

The fourier transform of $f(t)$ can be approximated, using a Riemann sum,
to

$$
    \tilde f(\omega) \simeq \sum_{j=0}^{N-1} \Delta t \ x_j \ e^{-i \omega t_j}
$$

Now say
$ \omega_k = 2 \pi k/ N \Delta t$.
Then we can rewrite the discrete fourier transform as

$$
    X_k = \sum_{j=0}^{N-1} x_j e^{-i \omega_k (t_j - t_0)} = e^{i \omega_k t_0} \sum_{j=0}^{N-1} x_j e^{- i \omega_k t_j}
$$

Hence we find

$$
    \tilde f(\omega_k) \simeq e^{-i \omega_k t_0} \Delta t X_k
$$

Since there are algorithms for the DFT which only take $\mathcal{O}(N \log N)$ time, instead of $\mathcal{O}(N^2)$ for
simple matrix multiplication,
this algorithm for approximating the analytical fourier transform also takes
only $\mathcal{O}(N \log N)$ time.

The approximation works well for frequencies up to $\omega << 1/\Delta t$

This comparison is depicted for the gate function:

$$ f(t) = \Theta(-|t - 1| + 2) $$

![Gate function]({{ "/assets/gate_function.png" | absolute_url }})

Below we can see how the approximate Fourier transform really approaches the
analytical Fourier transform closely.

![Comparison of discrete and analytical Fourier transforms]({{ "/assets/discrete_analytical.png" | absolute_url }})

This post was based on [this discussion][axelrod] and on [this question][math-se]. One can read more on the topic [here][upenn]

The Mathematica code for the figures and numerical evaluations
in this post is available as a [Github gist][gist].

[axelrod]: https://arxiv.org/abs/1508.01282
[math-se]: https://math.stackexchange.com/questions/388009/numerical-approximation-of-the-continuous-fourier-transform
[upenn]: https://www.math.upenn.edu/~cle/papers/fftvsft.pdf
[gist]: https://gist.github.com/gapolinario/4d3b7f64ad790e458c47837d0a3f5024

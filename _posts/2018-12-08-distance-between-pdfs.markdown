---
layout: post
title:  "Distance Between PDFs"
date:   2018-12-08 18:00:00 -0200
categories: math
---

Imagine you have a probability density function (PDF) obtained experimentally,
and would like to describe its features simply by measuring the
mean and standard deviation of this PDF. How wrong can you be?

There are several ways to measure the distance between two
PDFs, I am going to use the [Hellinger distance][helli].
It was chosen because it is symmetric on the distributions,
bounded between 0 and 1 and satisfies the triangle inequality.

It is given by

$$
H_D(P, Q) = \sqrt{1 - BC(P,Q)} .
$$

$BC(P,Q)$ is the Battacharyya coefficient, it is

$$
BC(P,Q) = \sum_a \sqrt{p(a)q(a)}
$$

for discrete probability distributions and

$$
BC(P,Q) = \int \sqrt{p(x)q(x)} dx
$$

for continuous distributions.

If two distributions match exactly, their distance is $D_H = 0$,
whereas they are maximally distant if $D_H = 1$.

Now we know how to measure the distance between two distributions,
and the question is:
How large can the Hellinger distance be between two distributions
which share the same mean and standard deviation?

The [Vysochanskiij-Petunin (VP) inequality][vyso]
is one of many inequalities in statistics and probability,
it places an upper bound on the probability
of rare events. The VP inequality is valid for unimodal distributions
and states that

$$
\mathbb{P}[|X - \mu| \geq \lambda \sigma] \leq	\frac{4}{9 \lambda^2}
$$

for any $\lambda > \sqrt{8/3}$.

A more general inequality is the [Chebyshev inequality][cheb],
which itself is a corollary of the [Markov inequality][mark].

The distribution which satures the VP inequality, for a given $\lambda$, is

$$
P = 
\begin{cases}
	1 - 4/(3 \lambda^2) \ \mbox{ ,  at  } \ x = \mu \\
	4 / 9 \lambda^3 \sigma \ \mbox{ , if } \ x \in 
	[\mu - 3 \lambda \sigma/2, \mu + 3 \lambda \sigma /2] - \{\mu\}
\end{cases}
$$

The classic distribution which displays only small fluctuations
is the Gaussian, I am going to calculate the distance between
the above distribution and a Gaussian, both with mean $\mu = 0$
and standard deviation $\sigma$, as an estimate of the largest distance
between two distributions.

The Battacharyya coefficient for these two distributions is

$$
BC = \sqrt{\frac{4}{9 \lambda^3 \sigma^2 \sqrt{2\pi}}} \int_{-3\lambda\sigma/2}^{3\lambda\sigma/2} e^{-x^2/4 \sigma^2} dx
+ \sqrt{\frac{1}{\sqrt{2 \pi} \sigma} \left( 1 - \frac{4}{3 \lambda^2} \right)}
$$

In the limit of very large fluctuations, $\lambda \rightarrow \infty$,
the first term is canceled and we are left with

$$
H_D = \sqrt{1 - \frac{1}{\sqrt[4]{2 \pi \sigma^2}}}
$$

For small standard deviations, the maximum distance is small.
But there is no intrinsic bound, it can be as close to one
as desired. This can be seen in the table below

| $\sigma$ | $H_D$ |
|:--:|:--:|
| 0.5 | 0.327 |
| 1.0 | 0.607 |
| 2.0 | 0.744 |
| 3.0 | 0.895 |

[helli]: https://en.wikipedia.org/wiki/Hellinger_distance
[vyso]: https://en.wikipedia.org/wiki/Vysochanskij%E2%80%93Petunin_inequality
[cheb]: https://en.wikipedia.org/wiki/Chebyshev's_inequality
[mark]: https://en.wikipedia.org/wiki/Markov's_inequality
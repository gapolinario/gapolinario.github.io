---
layout: post
title:  "Notes on Landau asymptotic notation"
date:   2018-02-27 20:00:00 -0200
categories: physics
math: true
---

These notes are based on this [Khan academy][khan]
lecture notes, which are very clear and have some
examples.

$g(n) = \Theta(f(n))$ means that, for large enough $n$, 
the function $g(n)$ is between $k_1 \cdot f(n)$
and $k_2 \cdot f(n)$, for some values of $k_1$
and $k_2$. Big-$\Theta$ notation
is an **asymptotically tight bound**,
since it bounds the function $g(n)$
from above and below.

One might want to bound only from above, and
this is the function of big-O notation.
Thus $g(n) = O(f(n))$ means that,
for large $n$, $g(n)$ is at most $k \cdot f(n)$.
Thus big-O is used for **asymptotic upper
bounds**.

Notice what $O(f(n))$ being an upper bound
means. If I assert the running time
of binary search is $O(n)$, I am correct,
although the bound could be made more
strict, to $O(\log n)$. Although if I
say binary search is $\Theta(n)$,
I am not correct. I can only say
binary search is $\Theta(\log n)$ in the worst
case, but I can always say its running time
is $O(\log n)$, or even $O(n)$.

And now for lower-bounds, we have big-$\Omega$
notation. If a function $g(n)$ is
$\Omega(f(n))$, then it is bounded
below by $k \cdot f(n)$, for some $k$.

Notice also that $\Theta(f(n))$ implies
both $O(f(n))$ (an upper bound)
and $\Omega(f(n))$ (a lower bound).

The course gives examples of algorithm
running times, and these are very clear.
But they are always in the limit of
$n$ very large.
Physicists also tend to use this notation
for vanishingly small quantities, like
$\varepsilon$ approaching zero,
where large and small exponents trade places.

[khan]: https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/asymptotic-notation

---
layout: post
title:  "Grönwall's Inequality"
date:   2018-09-18 10:00:00 -0300
categories: math
---

Grönwall's inequality is one of the fundamental results in
the theory of ordinary differential equations,
as recently pointed out by [Terry Tao][tao],
with far reaching applications in the theory of
regularity and well-posedness of nonlinear
differential equations.

Consider the differential inequality

\begin{equation} \label{ineq}
\partial_t u(t) \leq A(t) u(t) + F(t)
\end{equation}

where $u,F,A : I \rightarrow \mathbb{R}$
are continuously differentiable functions
and $I$ is an interval of the form
$[0,a]$, $[0,a)$ or $[0,\infty)$,
given $a > 0$.
We also have the initial condition $u(0) = u_0$.

Grönwall's theorem states the following inequality:

$$
u(t) \leq u_0 \ \exp \left( \int_0^t A(t') dt'\right)
+ \int_0^t F(s) \ \exp \left( \int_s^t A(t') dt' \right) ds
$$

Notice that the right-hand side is the solution
of the differential _equality_
analogous to \eqref{ineq}.

**Proof**

The integrating factor for this equation is
$\exp \left( -\int_0^t A(t') dt' \right)$, hence we
can rewrite \eqref{ineq} as

\begin{equation}
	\partial_t \left[ u(t) \ e^{-\int_0^t A(t') dt'} \right]
	\leq
	F(t) \ e^{-\int_0^t A(t') dt'} \ .
\end{equation}

The last equation can be integrated as

$$
u(t) \ e^{-\int_0^t A(t') dt'} \leq u_0
+ \int_0^t F(s) \ e^{-\int_0^s A(t') dt'} \ ds
$$

and simplified to give

$$
u(t) \leq u_0 \ e^{\int_0^t A(t') dt'}
+ \int_0^t F(s) \ e^{\int_s^t A(t') dt'} \ ds \ .
$$

This completes the proof. $\blacksquare$


Incidentally, the final inequality,
and the demonstration, do not rely on
the direction of the inequality,
or on specific signs of the $A,F$
functions, hence one can apply the same
inequality backwards,
and obtain upper and lower bounds
for a differential equation.

Say there is a complicated function
$F(t)$ such that

$$
\partial_t u(t) = A(t) u(t) + F(t) \,
$$

and one would like to obtain
rigorous estimates on the solution.
This can be done with
upper and lower bounds, using Grönwall's inequality.

We can look for $F_1(t)$ and $F_2(t)$ such that
$F_1(t) \leq F(t)$ and $F_2(t) \geq F(t)$ on $I$,
this implies

$$
A(t) u(t) + F_1(t) \leq \partial_t u(t) \leq A(t) u(t) + F_2(t)
$$

and from the above theorem we conclude that

$$
u_0 e^{\int_0^t A(t') dt'}
+ \int_0^t F_1(s) e^{\int_s^t A(t') dt'} ds
\leq
u(t)
\leq
u_0 e^{\int_0^t A(t') dt'}
+ \int_0^t F_2(s) e^{\int_s^t A(t') dt'} ds
$$

These are upper and lower bounds
on the solution of the exact, complicated, differential equation,
but depending on the forms of $A$, $F_1$ and $F_2$,
might give exact and more tractable solutions.

For more references on the topic, you can lookup the
Wikipedia page on [Grönwall's inequality][gronwall]
and its references.


[tao]: https://terrytao.wordpress.com/2018/09/16/254a-notes-1-local-well-posedness-of-the-navier-stokes-equations/
[gronwall]: https://en.wikipedia.org/wiki/Gr%C3%B6nwall%27s_inequality
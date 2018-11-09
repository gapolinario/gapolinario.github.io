---
layout: post
title:  "Concepts in Probability Theory"
date:   2018-11-09 12:00:00 -0300
categories: math
---

This is a review of the main mathematical definitions
and concepts
in the theory of probability and stochastic processes.
Each concept is illustrated with an example
from simple random processes (dice throws, random
walks and the Wiener process).

Many of these concepts are based on ideas from
measure theory, that have allowed probability theory
to unify
discrete and continuous random variables and precisely
state its results. But I do not aim at being mathematically
rigorous with this notes, only to get acquainted with
the definitions and ideas, through examples.

## Probabilities

A probability space is a triple $(\Omega, \mathcal{A}, P)$
consisting of

1. The _sample space_ $\Omega$: This is the set of all possible outcomes.
1. A $\sigma$-algebra (sigma-algebra) $\mathcal{A}$, its elements
are all the observable _events_.
1. A probability measure $P$, which assigns to each event $X \in \mathcal{A}$ a probability $P(X)$.

In the throw of a regular dice, for instance, 
there are six possible outcomes, they consitute the sample space:
\begin{equation}
\Omega = \\{ 1, 2, 3, 4, 5, 6 \\}
\end{equation}
Regarding dice throws and this sample space, there
are several probabilistic questions one could ask,
for instance:

What is the probability of ...

1. ... getting a 1?
1. ... not getting a 6?
1. ... rolling a number larger than 3?
1. ... rolling a sum of 6 with two dice?
1. ... getting a sum of more than 9 with two dice?
1. ... rolling a sequence of 3 ones in 10 dice throws?

All these, and many more, are possible events,
each of them with a probability.
The set which describes all these events is the $\sigma$-algebra
$\mathcal{A}$.
From these questions you can have an idea of
what are the elements of $\mathcal{A}$,
and in the next section
I will describe what is and what are the properties
of a $\sigma$-algebra.

Another example of a random process is the random walk.
In it,
a walker starts at the origin of one-dimensional space,
for instance, 
 and at each time step,
randomly walks one unit to the left or right.
The possible outcomes for each step
are only $\Omega = \\{R,L\\}$.
But the events observed are walks
of several steps, hence one could ask questions such as

What is the probability of ...

1. ... being 10 steps away from the origin after 100 timesteps?
1. ... returning to the origin after 200 timesteps?
1. ... being 50 steps away from the origin in less than 200 timesteps?
1. ... visiting the origin more than 10 times in 100 timesteps?

And obviously many other questions.
All of these questions are possible observable events
in a random walk, and correspond to elements
of the $\sigma$-algebra $\mathcal{A}$ of the random walk
probability space, each with an assigned probability.

A third example is the Wiener process, or
Brownian motion, similar to a random walk
but happening on continuous time.

The probabilities one asks about regarding
the Wiener process are (not exclusively) of the form:

$$P(X(t) \leq x)$$

$$P(X(t_1) \leq x_1, X(t_2) \leq x_2)$$

$$P(X(t_1) \leq x_1, X(t_2) \leq x_2, X(t_3) \leq x_3)$$

With these examples in mind, we can move to the next example

## What is a $\sigma$-algebra?

A $\sigma$-algebra $\mathcal{A}$ is
a collection of subsets of the set $\Sigma$,
such that it satisfies the following properties

1. $\Sigma$ and the empty set ($\emptyset$) are both elements of $\mathcal{A}$.
1. (Closed under complement) if $X$ is an element of $\mathcal{A}$, then its complement $X^c = \Omega - X$
is also an element of $\mathcal{A}$.
1. (Closed under countable union) If $X_1, \ X_2, \ldots$ are all elements of $\mathcal{A}$,
then their union, $\cup_{i=1}^{\infty} X_i$ must also be an
element of $\mathcal{A}$

These requirements are aligned with
the intuitive notions of probability,
which are formalized by the [Kolmogorov axioms][k33].
The first axiom is that probabilities must
be non-negative real numbers.

The second axiom is the assumption of
_unit measure_:
At least one of the events is certain to happen
(it happens with probability 1,
mathematically: $P(\Sigma) = 1$).
Hence $\Sigma$ must be an event present in the $\sigma$-algebra.

The second and third points in the definition of
the $\sigma$-algebra are related to the
third axiom. It states that countable unions
of disjoint sets $E_1, E_2, \ldots$ satisfy:

$$ P \left( \bigcup\limits_{i=1}^{\infty} X_i \right)
= \sum_{i=1}^{\infty} P(X_i) $$

In the definition of the $\sigma$-algebra,
together with the first two axioms,
this means that:
- if there is a probability for an event 
$X$, there must also be a probability for its complement,
$X^c$.
- and if there are probabilities for two events,
there must also be a probability for either of them
happening.

**Examples of $\sigma$-algebras**

Given the set of dice throws: $\Omega = \{1,2,3,4,5,6\}$,
some possible sigma algebras are:

$$
\mathcal{A_0} = \{ \emptyset, \Omega \}$$

(This is the trivial $\sigma$-algebra, it contains only the empty
set and $\Omega$ itself).

$$
\mathcal{A_1} = \{ \emptyset, \{1\}, \{2,3,4,5,6\}, \Omega \}
$$

$$
\mathcal{A_2} = \{ \emptyset, \{1,2,3\}, \{4,5,6\}, \{1,2,3,4,5,6\} \}
$$

The _power set_ of $\Omega$ is also an important $\sigma$-algebra,
it is defined as the set of all subsets of $\Omega$,
including the empty set and $\Omega$ itself.
A common notation for the power set is $2^{\Omega}$.

$2^{\Omega}$ is the $\sigma$-algebra corresponding
to one dice throw. Any observable event is in this set.
For a number $N$ of dice throws, the corresponding
$\sigma$-algebra is 

\begin{equation}
\underbrace{2^{\Omega} \times 2^{\Omega} \times \cdots
\times 2^{\Omega}}_{\text{$N$ times}}
\end{equation}

A similar reasoning holds for the random walk,
with a much smaller power set.

Given $\Omega = \mathbb{R}$,
which is the sample space of the Wiener process,
one can build a $\sigma$-algebra consisting of all open intervals
on the real line, and all countable unions, countable intersections
and relative complements, iteratively repeating this procedure
until satisfying all properties of this algebra,
this is known as the [Borel hierarchy][BH]

## Some book references

These books are rigorous, math-oriented, but are not
heavy on the demonstrations, or on assumptions
on the reader, quite adequate for a physicist.
Wikipedia and Stack Exchange were useful resources in finding simple examples too.

- Robert W. Keener. *Theoretical Statistics: Topics for a Core Course*. Springer, 2010.
- Philip E. Protter. *Stochastic integration and differential equations*. Springer, Berlin, Heidelberg, 2005.
- Fima C. Klebaner. *Introduction to Stochastic Calculus with Applications*. Imperial College Press, 2005.

A discussion on the intuition behind $\sigma$-algebras
is also available [here][sigmaSE].

[k33]: https://en.wikipedia.org/wiki/Probability_axioms#
[BH]: https://en.wikipedia.org/wiki/Borel_hierarchy
[sigmaSE]: https://stats.stackexchange.com/questions/199280/why-do-we-need-sigma-algebras-to-define-probability-spaces
---
layout: post
title:  "Undecidable Problems"
date:   2017-11-09 13:00:00 -0200
categories: physics
math: true
---

A list of undecidable problems.
These problems cannot be efficiently solved on a computer.

Is the 3D Ising Model undecidable or NP-complete?, Sorin Istrail

Graph-Isomorphism has an n^log n^O(1) algorithm,
due to Babai 2016, but it is not NP-complete.
The algorithm is not poly(n), but it has some complexity

What does it mean for a problem to be NP-complete, that
the best algorithm is necessarily exponential?
Or what is the algorithmic complexity of the best
solution to an NP-complete problem?

Why does everyone, everywhere, say the problem simply
cannot be solved?

Luca says humans can solve problems that computers cannot.
A formalization of this assertion would be to say
humans have some NP-oracle in their heads, which
Aaronson claims to be false, since we are not very good
at finding proofs, we just have some good people
who have done that.

An analytical solution necessarily means a linear
algorithm? Or at most exponential?

Plus, the articles say the computer can find
a transition temperature (which can be formulated
as a decision problem, just like local hamiltonians),
but this is false, computers can only do so for
the finite size problem, which is different from
the periodic boundary, or the infinite size Ising model.

Why doesn't anybody talk about this difference?
I'd have to read more of Istrail's text to know a little about it.
Maybe the finite 3D Ising model is not NP-complete.
Or is it?

The [article][pak] of Igor Pak for the 2018 ICM brought
some light onto this topic, or rather brought some more
formalization, which I still have to study.

One may consider the solution of the 1D Ising model
as a sequence of numbers for its partition function:

$$Z_N = 2^N ( \cosh(J/\beta))^{N-1}$$

McCoy and Wu furnish a solution for the 2D Ising model
which has exactly the connection that I would like to
make, on page 78:

The problem of evaluating Z is therefore equivalent
to the problem of finding the generating function for closed,
and possibly intersecting,
polygons with p horizontal and q vertical sides on the
square lattice, with the restriction that no two sides may overlap.

The fact that the 3D Ising model is NP probably means
the fact that one might have a generating
function for Z_N which is hard to calculate
(that is, a generating function without a Wilfian W1 formula),
but which can be verified in polynomial time.
But how can that be? How can we reconcile these two
apparently contradictory senteces?
And what does it mean to verify the value of
the partition function in the Ising model?
How can one verify such an answer in polynomial time?

A brief description of a W1 formula is suited, following the
definition [here][pak] or another one.
A mention of Wilf, What is an Answer, would also
be suited, where he comments that there might be answers
which are more complex to evaluate than brute force
examination of cases, directly.



Article is [here][istrail]

[istrail]: https://pdfs.semanticscholar.org/5e99/c1fb44e251464e2928f00766104708ef61fe.pdf
[pak]: https://arxiv.org/abs/1803.06636

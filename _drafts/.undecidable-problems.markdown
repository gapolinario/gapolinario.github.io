---
layout: post
title:  "Undecidable Problems"
date:   2017-11-09 13:00:00 -0200
categories: physics
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

Article is [here][istrail]

[istrail]: https://pdfs.semanticscholar.org/5e99/c1fb44e251464e2928f00766104708ef61fe.pdf

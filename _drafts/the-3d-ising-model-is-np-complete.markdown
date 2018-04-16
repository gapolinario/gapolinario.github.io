---
layout: post
title:  "Undecidable Problems"
date:   2017-11-09 13:00:00 -0200
categories: physics
math: true
---

I recently learned of the demonstration
that the 3D Ising model is NP-complete.

Barahona demonstrated that finding the ground state is NP-hard

and Sorin Istrail demonstrated it is NP-complete,
though with a confusion on what is really NP-complete,
since he did not talk of a decision problem,
but of a function problem

A list of undecidable problems.
These problems cannot be efficiently solved on a computer.

Barahona demonstrated

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


## Talk about P \neq NP

Living on the assumption that $ P \neq NP $, what does the result of Sorin Istrail
for the NP-completeness of the Ising model mean for analytical results?

Everywhere it is said it is death of analytical results. Well, only of
analytical results on the lattice.

Luca says not so, because humans can come up with non-algorithmic
steps, which can be verified simply. But a full analytical result
would mean the answer can be written in polynomial time
for any lattice size. This means, if we assume $P \neq NP$,
then there cannot be an analytical result for 
the 3D Ising model.

Istrail does not mention the implications

Then the bootstrap paper says that an analytical solution for the
continuous model can still be found.

> Now Sandia computational biologist Sorin Istrail has shown that the solution of Ising¹s model cannot be extended into three dimensions for any lattice, and so exact solutions can never be found.

> What these brilliant mathematicians and physicists failed to do, indeed cannot be done.

Sorin himself

Here: http://www.sandia.gov/LabNews/LN04-21-00/sorin_story.html

McCoy book has solution to Ising model and Pfaffian too.

The question is what is the free energy, or what is the partition function, these are equivalent.

Ernst Ising proposed the model in his PhD thesis and showed there is no phase transition for the model in 1D.

Lars Onsager answered this question for the 2D Ising Model in

McCoy book has a summary of dates and researchers who have brought advances to the Ising model (the newest entry is from 2007, and the book is already some years old)

Istrail contribution is from what year?

In 10.1.1, McCoy displays the solution for the Ising model on the torus with Lv and Lu rows/columns.
The solution can be found in polynomial time, because it is given in terms of an explicit formula

Q: Can the solution be found in terms of a recursive formula that takes exponential time
to be directly evaluated? Does this make any sense? If it could, could
the formula be checked, as is required for NP problems?

This means the 2D Ising model is P, one can simply determine the solution by
means of the analytical lattice solution, and this is the best algorithm for it.

Evaluate the time it takes to evaluate that function, it has a finite product,
pay attention (10.2 McCoy solution).

The converse is, 3D Ising model is NP-complete, resting on the inequality of P and NP,
we have that exact formulas for the 3D lattice can't be found, not even by
divine guess, as Luca proposed.


- What does this mean for the Istrail assertion that 3D Ising model is NP complete
- Nature news: http://www.nature.com/news/2000/000426/full/news000427-4.html
- SIAM B. Cipra: https://www.siam.org/pdf/news/654.pdf
- A comment: https://arxiv.org/pdf/0811.1802.pdf
- SKlog wiki: http://www.sklogwiki.org/SklogWiki/index.php/Ising_model
- Science news: http://www.sciencemag.org/news/2000/05/physics-bumps-against-unsolvable
- Aaronson and NP completeness in Nature: https://www.scottaaronson.com/papers/npcomplete.pdf
- Istrail, apparently not the full article: https://pdfs.semanticscholar.org/5e99/c1fb44e251464e2928f00766104708ef61fe.pdf

Ising Conformal Bootstrap mentions Istrail ([article][boot]):
> In this paper, we will be aiming for a solution of the 3D Ising model in the continuum
  limit and at the critical temperature T = Tc. While the 2D Ising model was solved exactly
  on the lattice and for any temperature by Onsager and Kaufman in the 1940’s, the 3D lattice
  case has resisted all attempts for an exact solution. Istrail [28] proved in 2000 that solving
  the 3D Ising model on the lattice is an NP-complete problem. However, this theorem does
  not exclude the possibility of finding a solution in the continuum limit.

Saberi on his advances in percolation theory mentions istrail in passing: https://arxiv.org/pdf/1504.02898.pdf

Complexity for Physicists mentions Istrail only on a reference: https://arxiv.org/pdf/cond-mat/0012185.pdf

The Stanford course has a section on the philosophical implications of P=NP https://plato.stanford.edu/entries/computational-complexity/

[boot]: https://arxiv.org/pdf/1203.6064.pdf
[luca]: http://minimalist-thinking.blogspot.com.br/2007/12/p-np-np-c-and-ising-3d.html

https://pdfs.semanticscholar.org/5e99/c1fb44e251464e2928f00766104708ef61fe.pdf

http://go.galegroup.com/ps/i.do?id=GALE%7CA62924785&sid=googleScholar&v=2.1&it=r&linkaccess=fulltext&issn=00368075&p=AONE&sw=w&authCount=1&u=capes&selfRedirect=true

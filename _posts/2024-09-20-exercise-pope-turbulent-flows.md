---
layout: post
title: "An exercise from Pope, Turbulent Flows"
date: 2024-09-20 17:00:00 +0200
categories: turbulence, physics
---

This post discusses exercise 6.11 (p. 205) of Turbulent Flows, the book by S. B. Pope.

There is a database of solutions of this book [available online](https://pope.mae.cornell.edu/TurbulentFlows/solutions/index.html), however the solution to this exercise is not yet available. The problem uses symmetries of statistically homogeneous, isotropic and incompressible flows, to derive some properties of the one-point velocity gradient distribution. The velocity gradient of a fluid with velocity $u_i$ is defined by

$$
A_{ij} = \frac{\partial u_i}{\partial x_j}
$$

Below, the velocities and velocity gradients are always calculated at the same position $\vec{x}$, which is omitted from all formulas.

Let's start with an example that is simpler than the one in exercise 6.11, the two-gradient correlation function:

\begin{equation}
G_{ijkl} = \left\langle \frac{\partial u_i}{\partial x_j} \frac{\partial u_k}{\partial x_l} \right\rangle
\label{eq:def_G}
\end{equation}

Since the fluid is statistically isotropic, so is this observable. A general isotropic tensor with four indices can be written as

$$
G_{ijkl} = a \delta_{ik} \delta_{jl} + b \delta_{il} \delta_{jk} + c \delta_{ij} \delta_{kl}
$$

where the $\delta_{ij}$ are Kronecker deltas.

If we change the positions of the velocity gradients in Eq.~\ref{eq:def_G}, nothing changes, therefore

$$
G_{ijkl} = G_{klij}.
$$

This is automatically satisfied by the the definition above with the Kronecker deltas.

We also need to satisfy the incompressibility constraint:

$$
\frac{\partial u_i}{\partial x_i} = 0
$$

(Notice that Einstein notation is used, and summation over repeated indices is implied).
Therefore, we conclude that

$$
G_{iikl} = G_{ijkk} = 0,
$$

which generates the constraint

$$ a+b+3c = 0.$$

Finally, because of statistical homogeneity, we have

$$
\frac{\partial}{\partial x_j} \left\langle u_i \frac{\partial u_j}{\partial x_k} \right\rangle = 0,
$$

which is equal to

$$
G_{ijjk} = 0,
$$

and also

$$a+3b+c=0.$$

This implies a stricter and well-known result:

$$
\left\langle \frac{\partial u_i}{\partial x_j} \frac{\partial u_j}{\partial x_i} \right\rangle = 0.
$$

This is called a Betchov constraint, and is often written in terms of the velocity gradient tensor as

$$
\left\langle \mathrm{tr} \, A^2 \right\rangle = 0.
$$


We have now two equations for three variables. Let us choose $a=2 / \nu$, where $\nu$ is the viscosity, this is a traditional choice in the literature.
The result is

$$
G_{ijkl} = 2 \delta_{ik} \delta_{jl} - \frac12 \delta_{il} \delta_{jk} - \frac12 \delta_{ij} \delta_{kl}
$$

In this notation, the mean energy dissipation is

$$
\langle \varepsilon \rangle = 2\nu \left\langle S_{ij} S_{ij} \right\rangle = \nu \langle A_{ij} A_{ij} + A_{ij} A_{ji} \rangle = \nu ( G_{ijij} + G_{ijji} ) = 15
$$

This result has been used in several models of the velocity gradient dynamics, see for instance Refs. 2 and 3

## Exercise 6.11

Let's go to the exercise now: We're interested in a 6th order tensor,

$$
H_{ijklmn} = \left\langle  \frac{\partial u_i}{\partial x_j} \frac{\partial u_k}{\partial x_l} \frac{\partial u_m}{\partial x_n} \right\rangle.
$$

Write it as an isotropic tensor:

\begin{equation}
H_{ijklmn} = \sum_{p \in \mathcal{P}\\{i,j,k,l,m,n\\}} a_p \delta_{p_1,p_2} \delta_{p_3,p_4} \delta_{p_5,p_6},
\label{eq:def_H_iso}
\end{equation}

where we call the set of all permutations of the indices $\mathcal{P}\\{i,j,k,l,m,n\\}$ and we sum over all permutations. Each permutation is named $p$, and each element of it is indicated with an index, for instance:

$$p = \\{i,k,j,l,m,n\\} \ \mathrm{and} \ p_2 = k.$$

The enumeration of all permutations, as well as the next steps, were done with Mathematica, follow the link for [the accompanying code](https://github.com/gapolinario/pope-exercise-6-11).

To reduce the complexity of Eq.~\ref{eq:def_H_iso}, we appeal to the symmetries of $H$. First we have relabeling symmetry--there are three ways of rearranging the indices that keep the $H$ tensor invariant:

1. $H_{ijklmn} = H_{klijmn}$
2. $H_{ijklmn} = H_{ijmnkl}$
3. $H_{ijklmn} = H_{mnklij}$

This simplifies the tensor to the form given in Eq. 6.95 of the book:

$$
\begin{split}
H_{ijklmn}
&= a_{26} (\delta_{il} \delta_{jm} \delta_{kn} + \delta_{in} \delta_{jk} \delta_{lm}) \\
&+a_{19} (\delta_{in} \delta_{jl} \delta_{km} + \delta_{il} \delta_{jn} \delta_{km} + \delta_{im} \delta_{jl} \delta_{kn} + \delta_{ik} \delta_{jn} \delta_{lm} +
\delta_{im} \delta_{jk} \delta_{ln} + \delta_{ik} \delta_{jm} \delta_{ln}) \\
&+ a_{15} \delta_{ij} \delta_{kl} \delta_{mn} +
a_{17} (\delta_{in} \delta_{jm} \delta_{kl} + \delta_{ij} \delta_{kn} \delta_{lm} +
\delta_{il} \delta_{jk} \delta_{mn}) \\
&+a_{16} (\delta_{im} \delta_{jn} \delta_{kl} + \delta_{ij} \delta_{km} \delta_{ln} + \delta_{ik} \delta_{jl} \delta_{mn})
\end{split}
$$

The next constraint we have is incompressibility, which means:

$$
H_{iiklmn} = H_{ijkkmn} = H_{ijklmm} = 0
$$

Finally, we have another Betchov constraint (see Ref. 4, eq. 24):

$$
\langle A_{ij} A_{jk} A_{ki} \rangle = 
        \frac{\partial}{\partial x_i} \left\langle A_{ij} A_{jk} u_k - \frac12 u_i A_{kj} A_{jk} \right\rangle
        = 0
$$

This is a total derivative of a homogeneous quantity, therefore is zero. The relation we obtain from this constraint is

$$a_1 + 3 a_2 + 9 a_3 + 10 a_4 + 12 a_5 = 0,$$

instead of Eq. 6.97 of the book. This is mentioned in p. 6 of the [errata to the Pope book](https://pope.mae.cornell.edu/corrections.pdf).

Gathering all the constraints (relabeling, incompressibility and the Betchov constraint), all the free parameters $a_i$ are expressed in terms of a single free-parameter which captures the velocity-gradient skewness.

Equations 6.95 to 6.101 in the Pope book are then verified in the Mathematica code.

**References**

1. Pope, S. B. (2000). _Turbulent Flows_. Cambridge: Cambridge University Press.
2. Chevillard, L., & Meneveau, C. (2006). Lagrangian dynamics and statistical geometric structure of turbulence. _Physical review letters_, _97_(17), 174501.
3. Johnson, P. L., & Wilczek, M. (2024). Multiscale velocity gradients in turbulence. _Annual Review of Fluid Mechanics_, _56_(1), 463-490.
4. Betchov, R. (1956). An inequality concerning the production of vorticity in isotropic turbulence. _Journal of Fluid Mechanics_, _1_(5), 497-504.

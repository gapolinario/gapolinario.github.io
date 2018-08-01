---
layout: post
title:  "Mean Flow Profile in 2D Turbulence"
date:   2018-08-01 09:00:00 -0300
categories: physics
---

Recently there has been an advance in the problem of
determining the mean flow profile of a fluid in two dimensions.
In turbulence, fluctuations are strong, and their contribution
to the mean velocity profile cannot be neglected, this could be said
to be the source of difficulties in simulating flows at large Reynolds
numbers, and is translated as a need to model the Reynolds stress
tensor, $\langle u_i u_j \rangle$.

The [log law][frisch] is one of the predictions that could be
verified if a closed solution for the mean profile of a turbulent
flow in three dimensions were found.
In two dimensions, this has been done for a flow in a box with
periodic boundary conditions, in the paper
[Turbulence Statistics in a Two-Dimensional Vortex Condensate][anna].
The authors described and numerically verified the behavior of
the Reynolds stress tensor in this setting.

The quantity $\delta$ is a ratio between a large eddy time scale
and a small time scale, similar to a Reynolds number.
It is small, and this justifies the perturbative approach
that led to the results.

Their theory, combined with insights from the numerical simulations,
was able to show how the energy components, $\langle u^2 \rangle$
and $\langle v^2 \rangle$, and momentum flux component $\langle u v \rangle$
of the Reynolds stress tensor scale with the distance $r$ to the center
of the vortex, but now how they scale with $\delta$, what
has been determined numerically.

Previously, only the mean flux had been numerically verified.
The mean profile consists of a vortex condensate, which moves in time
on the same time scale as the vortices rotate.
The mean momentum flux, $\langle uv \rangle$ had been predicted,
but not verified, what is done in this article.

The energy contributions to the Reynolds tensor are solutions
to the equations describing fluctuations being advected
by the large scale flows. That is, the energy is determined
by advection at large scales only.

In the [LaurieEtAl][laurie] paper, they have obtained the mean
velocity and the mean momentum flux from energy balance considerations,
from the Navier-Stokes equations, thus both the external forcing
and shear flow are relevant to the momentum flux component,
which is accurately observed in the simulations.

The authors have used the freely available
[GHOST][ghost] software for the numerical simulations.

In a Quanta magazine [article][quanta], there are also reports of
experiments where two dimensional phenomena are relevant, such as hurricanes
and flows on the surface of Jupiter. Measurements
indicate that these flows are fed by the smaller scales,
contrary to three-dimensional flows.
The article comments that leaving the square geometry
of the article and exploring rectangular geometries leads
to completely different mean profiles, but is it possible that
the same techniques can be applied in this new context?


**Questions**

1. Under what conditions is there the inverse cascade?
At what scale does the forcing have to occur? Is the inverse cascade
universal in the external forcing and the boundary conditions?

2. How can one investigate the scaling of the Reynolds stress tensor
with $\delta$?

3. Can the same analysis be done for other two dimensional
geometries, such as bounded flows? The authors ask this question.
This is obviously looking forward to the problem of the log law
in wall flows and the flows on the surface of jupiter.

4. Can there be other simulation parameters, big enough, or small enough,
so that the observed convergence is close to the theoretical
region of convergence?

1. How can I see the momentum flux is determined by a balance between
external forcing and shear at small scales? Is this the argument
used in the [LaurieEtAl][laurie] paper?

1. The [LaurieEtAl][laurie] paper even goes to higher
order correlation functions.
These predictions should be verified, because the mechanism
for sustaining them might be the old one, the new one, or even
something else.


[frisch]: http://www.scholarpedia.org/article/Turbulence#Bulk_quantities.2C_drag_and_its_reduction
[anna]: https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.120.204505#supplemental
[ghost]: http://wp.df.uba.ar/mininni/ghost/
[laurie]: https://doi.org/10.1103/PhysRevLett.113.254503
[quanta]: https://www.quantamagazine.org/mathematicians-tame-turbulence-in-flattened-fluids-20180627/
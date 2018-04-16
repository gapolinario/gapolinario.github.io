---
layout: post
title:  "An argument for the Clausius theorem"
date:   2018-04-15 12:00:00 -0200
categories: [physics, thermodynamics]
---

The textbook used as reference for the basic
physics courses at UFRJ is the one written by Moysés.
In the second volume, there is an argument
to justify the Clausius inequality, which
is really misterious.

Consider a Carnot engine running between
temperatures $T_1$ (the hot source) and $T_2$
(the cold source).
The efficiency of this engine is
given by

$$ \eta = 1 + \frac{Q_2}{Q_1}
 = 1 - \frac{T_2}{T_1}, 
$$

where $Q_1$ and $Q_2$ are the heats
exchanged at the hot and cold sources,
respectively. We adopt the convention
that heat provided to the system is positive,
while heat extracted from it is negative,
hence the plus sign in the efficiency 
equation.

This is different from a common
convention used for thermal machines: Heat given to the system
by the hot source is positive
and heat extracted from the system by
the cold source is also positive.

From the above relation, we can see that

$$
\frac{Q_2}{T_2} + \frac{Q_1}{T_1} = 0 .
$$

This relation is valid for the Carnot
cycle only, a process where
there is exchange of heat only at these
two fixed temperatures $T_1$ and $T_2$.
But a similar construction can be built
for a general reversible cycle,
where we slice the cycle into small segments
built of small adiabatic and isothermal curves.
For each small segment we can adjust these adiabatic
and isothermal curves to match the work done
and heat exchanged so that they are equal
both in the original cycle and the new cycle,
which approximates the first one.

This new reversible cycle is a 
collection of Carnot engines, an infinite
collection in the limit where each of these
segments is infinitesimally small,
and the limit we obtain for the previous equation
is

$$
\oint_C \frac{dQ}{T} = 0 .
$$

This equation is valid for any reversible process,
and it tells us tells us there is a quantity
related to $dQ/T$ which is a state function, that is,
its variation does not depend on a particular cycle
chosen, only on the initial and final points.
A variation of entropy is defined by

$$
\Delta S = \int_C \frac{dQ}{T} .
$$

But for a general process we can still
build an argument which is similar to
equation the integral equation above.

If we had another engine, running a cycle
very similar to a Carnot cycle,
between the same temperatures
$T_1$ and $T_2$, though
irreversible, due to some small friction in the pistons,
for instance, its efficiency would be

$$
\eta_I = 1 + \frac{Q_2^I}{Q_1^I} < 1 - \frac{T_2}{T_1} ,
$$

which has an index $I$ everywhere to indicate
this is the irreversible cycle.

From the above equation we obtain that

$$
\frac{Q_2}{T_2} + \frac{Q_1}{T_1} < 0 ,
$$

similar to the equation for the reversible cycle, though this is an inequality.
This is valid for this engine, which is very similar
to a Carnot cycle and only operates between
two specified temperatures,
though we can still use the previous
construction to slice up a general
cycle into a large (infinite) collection
of small (infinitesimal) adiabatic and isothermal
curves, constituting a large number of contiguous
Carnot cycles, for which we would have,
in the limit

$$
\oint_C \frac{dQ}{T} < 0 .
$$

This is valid for any irreversible process.
Immediately we see that this knowledge can be summarized
as

$$
\oint_C \frac{dQ}{T} \leq 0 ,
$$

whatever process we are talking about,
reversible or not, this inequality holds, and
the equal sign holds only for reversible processes.

This last equation is known as the Clausius inequality,
which we wanted to prove following an argument
much simpler than the one in Moysés book.

The Clausius inequality is a mathematical description
of the second law of thermodynamics, which stems from
its qualitative formulations,
such as the Clausius and the Kelvin statements.
In this demonstration, we rely on the fact that
no engine can have an efficiency as large
as that of the Carnot cycle.

**Appendix:
What is the efficiency of the cycle built
of infinitesimal adiabatic and isothermal curves?**

Although the work and heat exchanged in
the original and the approximate cycles
are the same, one can demonstrate the
efficiencies are not the same,
as expected by the fact that the efficiency of the Carnot
cycle is maximum.

The efficiency of the new cycle, built of
adiabatic and isothermal curves only, is

$$
\eta = 1 + \frac{Q_2}{Q_1}
= 1 + \frac{\sum_i \delta Q_2^i}{\sum_i \delta Q_1^i},
$$

where $\delta Q_2^i$ and $\delta Q_1^i$ are
respectively the heat exchanged with the cold
and hot reservoirs at each small Carnot cycle,
and they are all infinitesimal.
We know these heat exchanges are each related by

$$
\delta Q_2^i = - \delta Q_1^i \frac{T_2}{T_1} ,
$$

and since they are infinitesimal,
we can choose every $\delta Q_1^i$
to be equal to a single $\delta Q$.
(Can you demonstrate this?)
This would mean the lengths of the partitions
on the $V$ direction are not all equal,
though the infinitesimal heat exchanged 
in each of these paths is.

It follows then that

\begin{equation}
\eta = 1 - \frac{\sum_i T_2^i/T_1^i }{N}, 
\end{equation}

where $N$ is the number of partitions we have made,
which goes to infinity in the limit.
The second term in the above equation is the average of the ratios
of $T_2^i/T_1^i$,
whereas in a Carnot cycle we would have
$T_2^{min}/T_1^{max}$,
which is the smallest such ratio.
And we know the average cannot be smaller than this minimum,
hence the efficiency of this new cycle is larger than
that of a Carnot cycle with the same maximal and minimal temperatures.

The efficiency of a cycle built of only adiabatic and
isothermal curves, but with heat exchanges at three temperatures,
is the topic of exercise 11 in chapter
10 of the Moysés book. One of the tasks is to
demonstrate the efficiency is smaller than that of
the Carnot cycle with only two temperatures.
This is not an infinitesimal example, hence we cannot choose
$\delta Q_1^i = \delta Q$.

- Nussenzveig, Herch Moysés. Curso de Física Básica: fluidos, oscilações e ondas, calor. Vol. 2. Editora Blucher, 2018
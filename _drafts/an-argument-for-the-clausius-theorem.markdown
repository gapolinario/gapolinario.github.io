---
layout: post
title:  "An argument for the Clausius theorem"
date:   2018-04-13 12:00:00 -0200
categories: [physics, thermodynamics]
---

I could not follow the argumentation in Moysés

Lookup Fermi

In the Carnot cycle, we can calculate and
observe that

$$
\frac{Q_2}{T_2} + \frac{Q_1}{T_1} = 0
$$

where we strictly follow the convention that
heat provided to the system is positive,
whereas heat extracted from the system is
negative.
This is different from a common
convention in thermal machines
which is: Heat given to the system
by the hot source is positive
and heat extracted from the system by
the cold source is also positive.

one could do the reverse argument, start from the fact that
the efficiency of a heat engine is always less than
that of the Carnot cycle,
run an irreversible "Carnot" cycle
and state that its efficiency are smaller than that
of carnot, this allows us
to obtain the inequality side
of the Clausius inequality.

Then one can do the mini-cycle argument
of breaking up the big general cycle
into small adiabatic and isothermal curves
which close on itself
and find out that the total dQ/T
is indeed smaller or equal to zero
and for a reversible process
one has that dQ/T is independent
on the path

We have for the Carnot cycle,
where we have a hot source at temperature
$T_1$ and a cold source at temperature
$T_2$,
considering strict adherence to
the thermodynamic convention that
heat absorbed by the system is positive,
while heat ceded is negative,
that its efficiency are

$$
\eta_R = 1 + \frac{Q_2}{Q_1} = 1 - \frac{T_2}{T_1}
$$

We then find that

$$
\frac{Q_2}{T_2} + \frac{Q_1}{T_1} = 0
$$

this is valid for a reversible
engine, where all heat exchanges
happen at fixed temperature
and all changes of temperature
involve no heat exchange

We can build another engine, which runs on a
cycle similar to Carnot, but which has some losses,
or it can run on any other cycle,
its efficiency will be

$$
\eta_I = 1 + \frac{Q_2}{Q_1} < 1 - \frac{T_2}{T_1}
$$

From these equations we can see that,
in an irreversible cycle,
we have

$$
\frac{Q_2}{T_2} + \frac{Q_1}{T_1} < 0
$$

The general argument then, is that

$$
\frac{Q_2}{T_2} + \frac{Q_1}{T_1} < 0
$$

irrespective of what type of cycle
this is, the equality holds
when we have a reversible engine,
whereas the inequality holds
for irreversible engines.

This is valid for a machine which runs an approximate,
irreversible version of the Carnot cycle,
but it also works for any other
cycle, as can be seen from a construction
which slices up any
thermodinamic cycle with small
pieces of adiabatic and isothermal curves

for each of these pieces we can match the work
and heat exchanges to that of the exact cycle,
and for an irreversible cycle we can approximate
it with a reversible cycle then follow this argument,
though this is not always true.


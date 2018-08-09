---
layout: post
title:  "Change of Variables in a Stochastic Integral"
date:   2018-07-23 10:00:00 -0300
categories: math
---

This is a very non-rigorous discussion on how to do a change of variables in
a stochastic integral.
I'm going to derive it in three different ways.

We would like to do the following stochastic integral:

$ \int_{t_1}^{t_2} F(t) dW_t $,

but for some reason it is easier to do a change of variables,
to some new variable $s(t)$. Let's study this in the simple case
when the change of variables is just a change of scale
$s = \alpha t$. This case can be generalized to
a more general setting.

**The First Way**

$W_t$ is a Wiener process, and its increments are i.i.d. normally distributed variables, with

$ \mathbb{E}[W_t] = 0$ and $\mathbb{E}[W_t^2]=t$.

One can also write

$ W_t = \int_0^{t} dW_t $

with the change of variables, $s = \alpha t$,
we'd have

$ W_t = \int_0^{\alpha t} J_{\alpha} dW_s $

where $J_{\alpha}$ is a Jacobian of this transformation,
we can guess it is a constant, due to the nature of the transformation.

The change of variables obviously does not change the result of the integration,
and if the result has the same distribution as the original result, $W_t$,
then they are equal. We are going to simply verify the mean and standard deviation
match.

Since $J_{\alpha}$ is a constant, we can pull it out of the integral and obtain

$ W_t = J_{\alpha} \int_0^{\alpha t} dW_s = J_{\alpha} W_{\alpha t} $

In order to have the same distribution in both sides,
we require the standard deviations of both sides
to be the same, thus
we need $J_{\alpha} = 1/\sqrt{\alpha}$,

then

$ dW_s = \frac{1}{\sqrt{\alpha}} dW_t $

**The Second Way**

An alternative approach, which involves less guessing but is no more
rigorous is:

We can say $ dW_t = \eta_t dt $, where $\eta_t$ is a delta-correlated process,
defined by:

$\mathbb{E}[\eta_t] = 0$ and $\mathbb{E}[\eta_{t_1} \eta_{t_2}] = \delta(t_1 - t_2) $

but the properties of the delta function are well known to allow for the change of
variables

We know that

$\mathbb{E}[\eta_{s_1} \eta_{s_2}] = \delta(s_1-s_2) = \delta(\alpha(t_1-t_2)) = \frac{1}{\lvert\alpha\lvert} \delta(t_1 - t_2) $

And from this we can argue that

$ \eta_s = \frac{1}{\sqrt{\lvert\alpha\lvert}} \eta_t $

In the integral, we have

$ W_t = \int_0^t \eta_{t'} dt' = \int_0^{\alpha t} \left( \sqrt{\alpha} \ \eta_s \right) \left( \frac{1}{\alpha} \ ds \right)
= \frac{1}{\sqrt{\alpha}} W_{\alpha t} $

And both ends of this equation are equal in distribution,
hence demonstrating the required change of variables.

**The Third and Simplest Way**

Simply require

$ \mathbb{E}[W_t^2] = \mathbb{E}[J_{\alpha}^2 W_{s(t)}^2] $

$ t = J_{\alpha}^2 \ s(t) $

$ J_{\alpha} = \sqrt{t / s(t)} = 1/\sqrt{\alpha} $

This last method looks more general, but it is not at
all rigorous, the final result is correct,
but the interemediate steps are not always valid.
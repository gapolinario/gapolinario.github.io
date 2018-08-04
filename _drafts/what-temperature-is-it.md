---
layout: post
title:  "What temperature is it?"
date:   2018-01-08 12:00:00 -0200
categories: physics
---

Here's an easy way to estimate the temperature
in Fahrenheit and Celsius conversion, within reasonable precision

Let's estimate human perception of temperature,
using Weber's law, let's say we can sense 3ºC differences 
on a reference temperature of 20ºC.

Then one can estimate the constant in Weber's law as

$ 3/20 = 15\% $

This is valid for Celsius graded temperatures, for Fahrenheit
scales, the constant is going to be rewritten as
(rounded up)

$ 6/68 = 8.8\% $

the latter is greater sensitivity, hence we have to be careful.

We know that the exact Conversion between Celsius and Fahrenheit is

$ TC = (TF - 32)/1.8 $

and that a difference of $\Delta_C$ degrees Celsius corresponds
to a change of $\Delta_F = 1.8 \Delta_C$ degrees Fahrenheit.

Let's approximate the conversion above to

$ TC' = (TF - 30)/2 $

We can measure the error $\varepsilon$ from this approximation
as the difference between the actual and approximated values,
the error relative to the actual value is going to be

$ \frac{| TC - TC' |}{TC} = \frac{|5 - 0.1 TF|}{TF - 32} $

there are two ways to do this, one is to measure this relative
to the 20ºC which I decided on originally, which is our reference
temperature, and is easier to generalize to other temperature
references.
This method of changing 32 to 30 and 1.8 to 2 looks
unique. Hence it looks better to consideres departures from ~20ºC/70ºF.


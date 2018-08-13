---
layout: post
title:  "What temperature is it?"
date:   2018-08-13 09:00:00 -0300
categories: physics
---

Here's an easy way to estimate the temperature
in Fahrenheit and Celsius conversion, within reasonable precision.

Let's estimate human perception of temperature,
using [Weber's law][weber]. If we can sense 2ºC differences 
on a reference temperature of 20ºC.

Then one can estimate the constant in Weber's law as

$ 2/20 = 10\% $

This is valid for Celsius graded temperatures, for Fahrenheit
scales, the constant is going to be rewritten as
(rounded up)

$ 3.6/68 \approx 5.3\% $

the latter is greater sensitivity, hence we have to be careful.

We know that the exact Conversion between Celsius and Fahrenheit is

$$ TC = (TF - 32)/1.8 $$

and that a difference of $\Delta_C$ degrees Celsius corresponds
to a change of $\Delta_F = 1.8 \Delta_C$ degrees Fahrenheit.

Let's approximate the conversion above to

$$ TC' = (TF - 30)/2 $$

We can measure the error $\varepsilon$ from this approximation
as the difference between the actual and approximated values,
the error relative to the actual value is going to be

$$ \frac{| TC - TC' |}{TC} = \frac{|TF - 50|}{10(TF - 32)} $$

This is the relative difference between the actual temperature
and the estimated temperature, and for a wide range of values,
it can be considered accurate within the $10\%$
tolerance that was estimated, as the figure below shows

![Relative error of approximate temperature conversion]({{ "/assets/celsius-approximation.png" | absolute_url }})

For all temperatures above 41ºF (5ºC), the
relative error is below $10\%$.
Whatismore, the limit
of this approximation as the fahrenheit temperature approaches infinity
is $10\%$, hence even very high temperatures work very well.

The inverse approximation, which is to take the exact Fahrenheit temperature

$$ TF = 1.8 TC +32 $$

for the approximation

$$ TF' = 2 TC + 30 $$

does not work so well. The relative error is

$$ \frac{| TF - TF' |}{TF} = \frac{|10 - TC|}{160 + 9 TC} $$

But this time the error must be below $5.3\%$ to correspond
to a similar error as that in the Celsius scale,
thus the approximation only works in the range between
1ºC (33.8ºF) and 35ºC (95ºF). There is also a figure for this case

![Relative error of approximate inverse temperature conversion]({{ "/assets/fahrenheit-approximation.png" | absolute_url }})

Note that this scale fails in the summer in tropical countries,
where the temperatures easily reach 40ºC (104ºF).

[weber]: https://en.wikipedia.org/wiki/Weber%E2%80%93Fechner_law
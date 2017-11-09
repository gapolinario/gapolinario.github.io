---
layout: post
title:  "Fourier Transforms with PyFFTW and Mathematica"
date:   2017-11-09 12:00:00 -0200
categories: [python, mathematica]
---

I struggled a little bit to get PyFFTW to work for the first time.
A test code Ze Hugo gave me was great help.
My first fourier transform was from Complex to Complex, it went like

```Python
import numpy as np
import pyfftw as ft

vin = ft.empty_aligned(8, dtype='complex128')
vout = ft.empty_aligned(8, dtype='complex128')
fft_plan = ft.FFTW(vin, vout, direction='FFTW_FORWARD')

vin = np.fromfunction(lambda i: np.cos(.1*i+.05)+np.sin(.1*i+.05)*1j, (8,), dtype=int)

fft_plan.update_arrays(vin,vout)
fft_plan.execute()
```

In the end, the `vout` array contains the Fourier transformed `vin` array.
Notice the Fourier transform that is done by FFTW is

```Latex
$$
Y_k = \sum_{j=0}^{n-1} X_j e^{-2 \pi i j k/n}
$$
```

On Mathematica, the same transform can be done with

```Mathematica
(Cos[.1 # + .05] + I Sin[.1 # + .05]) & /@ Range[0, 7]
Fourier[%, FourierParameters -> {1, -1}]
```

And this verifies indeed the Fourier transform does what it promised.

What also works: A Fourier transform from Real to Complex

```Python
vin = ft.empty_aligned(8, dtype='float64')
vout = ft.empty_aligned(5, dtype='complex128')
fft_plan = ft.FFTW(vin, vout, direction='FFTW_FORWARD', flags=('FFTW_MEASURE', ))
vin = np.fromfunction(lambda i: np.cos(.1*i+.05), (8,), dtype=int)
```
And this matches

```Mathematica
(Cos[.1 # + .05]) & /@ Range[0, 7]
Fourier[%, FourierParameters -> {1, -1}]
```

When doing the backwards transform, always remember to divide by n.

Transforms on only one of the axis also work, on Python they were done

```Python
vin = ft.empty_aligned((4,4), dtype='complex128')
vout = ft.empty_aligned((4,4), dtype='complex128')
f_plan = ft.FFTW(vin, vout, axes=(1,), direction='FFTW_FORWARD', flags=('FFTW_MEASURE', ))
b_plan = ft.FFTW(vout, vin, axes=(1,), direction='FFTW_BACKWARD', flags=('FFTW_MEASURE', ))

vin = np.fromfunction(lambda i, k: np.cos(.1*i+.2*k+.05)+np.sin(.1*i-.2*k+.05)*1j, (4,4), dtype=int)
f_plan.update_arrays(vin,vout)
f_plan.execute()
```

But the rows and columns are somewhat confusing, because the index 1 does
the Fourier transform over lines, apparently.
This matches the following Mathematica code:

```Mathematica
MA = Partition[(Cos[.1 #1 + .2 #2 + .05] + I Sin[.1 #1 - .2 #2 + .05]) & @@@ Tuples[{Range[0, 3], Range[0, 3]}], 4]
MB = Fourier[MA[[#, All]], FourierParameters -> {1, -1}] & /@  Range[Length[MA]]
```

So this is still a little confusing, best not to mix Python and Mathematica
to avoid errors coming up.

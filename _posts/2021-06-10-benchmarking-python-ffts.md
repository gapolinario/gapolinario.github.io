---
layout: post
title:  "Benchmarking Python FFTs"
date:   2021-06-10 9:00:00 +0200
categories: computing, python
---

These are some benchmarks on Fast Fourier Transform in Python using different tools: Numpy, Scipy, PyFFTW and PyTorch. The arrays are one-dimensional with complex entries and up to 2^26 elements.

Numpy and Scipy only run in one processor, while PyFFTW and PyTorch can be configured to run in multiple threads, and I tested them with 1,2,4 and 8 threads. The benefits of multithreading are significant both for PyFFTW and PyTorch, especially for larger arrays (> 2^14 elements).

For PyFFTW, I used the FFTW class, which involves transform plans, as the standard FFTW library in C. A suboptimal choice is to use the interfaces class, which is simpler to use since its syntax is the same as that of numpy.fft. The interfaces class is a little bit faster than the numpy Fourier transform, but it doesn't have one of the main benefits of the FFTW code, which are the planned transforms. Instead, it creates a new plan at every call. This can be very bad, especially if PyFFTW.interfaces is used with multithreading. In this last case, the overhead of communication and creating transform plans seriously overwhelm the benefits of the FFTW.

The performance of PyTorch for large arrays is impressive, with the smallest runtimes both for serial code and for the multithreaded code. I would also like to know what the results would be with GPU enabled on PyTorch. Can it be even faster?

{:refdef: style="text-align: center;"}
![Runtimes in linear and log scale]({{ "/assets/images/fft_times.png" | absolute_url }})
{: refdef}

The results were timed with the %timeit magic of jupyter notebooks, and can be seen in the figure above and the table below. The solid curves in the figure show the mean runtime, and the shaded area includes the minimum and maximum runtimes. Each color represents an array of different size, as indicated in the legend. The worst results come from numpy and PyFFTW.interfaces. The best results for smaller arrays come from PyFFTW.FFTW serial, and for larger arrays PyTorch multithreaded wins.

The table shows the ratio between the different modules and the numpy runtime, the most popular option. The smaller the number, the faster the module is compared to numpy. The best values for each array size are highlighted.

{:refdef: style="text-align: center;"}
![Ratio of runtime versus numpy runtime. Best values for each array size are highlighted]({{ "/assets/images/fft_table.png" | absolute_url }})
{: refdef}

The code is available on [Github][gist], as always.

[gist]: https://gist.github.com/gapolinario/cead51b4cdb56b63664963072bd712f8

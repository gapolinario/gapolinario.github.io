---
layout: post
title:  "Installation of PyFFTW"
date:   2017-11-07 18:00:00 -0200
categories: [linux, python]
---

It was sort of a complicated install process,
I had several problems.
First I had to update `pip`:

    sudo -H pip install --upgrade pip

Then to install `python3-dev` I had to remove
some conflicting packages, with

    sudo apt autoremove

And then

    sudo apt-get install python3-dev

Only then I downloaded FFTW3 and PyFFTW with

```
sudo apt-get install libfftw3-dev libfftw3-doc
pip install pyfftw
```

Probably, some of these steps are not strictly
required. But I've had this problem
to upgrade `pip` before and this may serve
to solve it in the future.

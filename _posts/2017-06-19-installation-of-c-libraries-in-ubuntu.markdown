---
layout: post
title:  "Installation of C libraries in Ubuntu"
date:   2017-06-19 12:00:00 -0200
categories: linux
---

I downloaded the libraries from their official websites:
<a href="http://www.fftw.org/download.html">FFTW</a>,
<a href="https://www.gnu.org/software/gsl/">GSL</a> and
<a href="http://www.feynarts.de/cuba/">Cuba</a>.
Then unzipped them with

    tar -zxvf file.tar.gz

The options stand for eXtract, Verbose and File.
For both packages, then, all I had to do was go to the
folder where they were extracted and run the standard sequence

```
 ./configure
 make
 sudo make install
```

Many libraries only need this to be installed and configured properly.

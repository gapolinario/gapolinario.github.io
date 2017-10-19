---
layout: post
title:  "Binary Files on Mathematica and Numpy"
date:   2017-09-24 12:00:00 -0200
categories: [mathematica, python]
---

Here is a program to assess that `BinaryReadList` has interpreted my data
accurately. Say I have generated a binary file and a text file
with the exact same double precision data (generated with a C
program, for instance). I can read them both in Mathematica with:

```
dataTxt = ReadList[path_to_txt_file_, Real]
dataBin = BinaryReadList[path_to_binary_file, "Real64"]
```

And both will hold the same data.

With Numpy, one can do the same, and the formating of the floating
point numbers is similar.

```
txtdata=np.loadtxt(path_to_txt_file)
bindata=np.fromfile(path_to_binary_file, dtype=np.float64)
```

Apparently, one can load a text file with `np.fromfile`, but I could
not do it.

A reference on all numpy data types can be found [here][numpy-types].

[numpy-types]: https://docs.scipy.org/doc/numpy-1.10.1/user/basics.types.html

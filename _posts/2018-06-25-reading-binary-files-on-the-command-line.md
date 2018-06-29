---
layout: post
title:  "Reading Binary Files on the Command Line"
date:   2018-06-25 17:00:00 -0200
categories: linux
---

I generated a binary file in Mathematica with
a list of real numbers (encoded in 64 bits, or standard double precision).

Generate the file in Mathematica with:
```
BinaryWrite[ path-to-file, data, "Real64" ]
```

To read this file on the command line, type
```
od -A n -t f8 "file"
```

`A` is the output format, `n` stands for none.

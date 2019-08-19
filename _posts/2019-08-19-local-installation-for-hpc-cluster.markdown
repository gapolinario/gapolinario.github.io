---
layout: post
title:  "Local Installation for HPC Cluster"
date:   2019-08-19 15:00:00 -0300
categories: [linux, hpc]
---

To have my programs running in an HPC cluster, I had to perform
some local installations

For the Pyhton packages

```
pip install --user package-name
```

GNU Parallel is a program to execute simple programs in parallel

To install it locally (with the help of [this link][par]):

```
wget https://ftpmirror.gnu.org/parallel/parallel-20190722.tar.bz2
tar -xvf parallel-20190722.tar.bz2
./configure --prefix=$HOME/.local/ && make && make install
```

[par]: http://git.savannah.gnu.org/cgit/parallel.git/tree/README
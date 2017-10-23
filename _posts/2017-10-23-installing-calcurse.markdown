---
layout: post
title:  "Installing calcurse"
date:   2017-10-23 11:00:00 -0200
categories: linux
---

The official documentation for [calcurse][calcurse]
demonstrates it would be a great surprise not to have the
`ncurses` library installed. But I didn't have.

This is an application used to display GUI-like interfaces
at a terminal, hence it is used by `calcurse`.
So I installed `ncurses` with

    sudo apt-get install libncurses5-dev libncursesw5-dev

And download `calcurse` source files, then it was simple to
install them following the classic linux installation path
described in the [c libraries post][c-libs].

There is also the fact to point out that `calcurse` was written
in C, since it requires a C compiler, quite different
from `jekyll`, `jupyter` and other programs which were
installed directly with `gem` or `pip`. These two programs
make me curious about what the future of linux and its source
code will be like. Still C in its major part? Or not?


[calcurse]: http://calcurse.org/
[c-libs]: {% post_url 2017-06-19-installation-of-c-libraries-in-ubuntu %}

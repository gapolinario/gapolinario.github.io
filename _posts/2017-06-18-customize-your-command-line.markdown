---
layout: post
title:  "Customize your Command Line"
date:   2017-06-18 13:00:00 -0200
categories: [linux, cli]
---

The PS1 variables stores the look of you command line prompt, you can take a look at its format,
right now, with

    echo $PS1

To change this look, I added the following line to the '~/.bashrc' file:


    export PS1="\[\033[1;36m\]\u@\h \[\033[0;36m\]\W > \[$(tput sgr0)\]"


This way, the terminal will be bold light blue (1;36m) and normal light blue (0;36m), you can choose other colors
and other formats for the terminal.

References on these colors are available at [this site][colors], for instance.

There are also <a href="http://bashrcgenerator.com/">bash rc generators</a>, which help you build one.

Then make changes permanent with


    source ~/.bashrc

[colors]: http://misc.flogisoft.com/bash/tip_colors_and_formatting

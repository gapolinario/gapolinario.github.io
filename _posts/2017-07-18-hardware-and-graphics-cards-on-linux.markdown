---
layout: post
title:  "Hardware and Graphics Cards on Linux"
date:   2017-07-18 11:00:00 -0200
categories: linux
---

To find out what is my graphics card, I tried


    lspci -vnn | grep VGA -A 12


This command shows all peripherals connected to the computer. VGA looks for
the graphics card line. On my computer, the output was



Where the model of the graphics card is Intel Broadwell-U Integrated Graphics [8086:161e]. This is on the line
of the 'VGA compatible controller'. The first number is the manufacturer, the second is the model.
There is also a Kernel driver in use also, but I looked for it in another manner, as we'll see.



I knew what is the model of my graphics card and I also wanted to know that graphics card driver is running. Is
it intel or not? I had this question after looking up intel on the web and found out they have open source
software for their graphics cards (not fact checked, but that is what they say). I then run


    lshw -c video



lshw is used to show all information on the hardware. In the output there is 'configuration driver',
which says what is the graphics driver in use.

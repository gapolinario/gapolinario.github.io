---
layout: post
title:  "What you can do with dd"
date:   2017-09-03 12:00:00 -0200
categories: linux
---

Here are some things I learned about the dd command from
this Joe Collins <a href="https://www.youtube.com/watch?v=BisJBC93sjQ">
video</a>.

He writes an ISO to a thumb drive, as I have already explained here, with

    sudo dd if=ubuntu.iso of=/dev/sdc

Then you can clear this same thumb drive with just zeros using

    sudo dd if=/dev/zero of=/dev/sdc

/dev/zero is a system device which outputs only zeros, one can also use
/dev/random is similar, but outputs random data all the time.
Say the drive is really large, you can clear just part of it adding
`bs=1M count=1024` to the end of the last command, and it still shows
up as blank.

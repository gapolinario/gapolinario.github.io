---
layout: post
title:  "How to view disk usage"
date:   2017-06-23 12:00:00 -0200
categories: linux
---

Display usage of disk for all partitions, including free space, with

    df -h

`-h` means human readable form.

And to display size of a single folder, or file, use


    du -sh /path-to-folder/


One nice trick is how to display size of all folders

    du -sh */


Take a look at the manual entries for df and du for more information.

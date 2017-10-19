---
layout: post
title:  "Creating links"
date:   2017-09-08 12:00:00 -0200
categories: linux
---

You can create a soft link to another file with

    ln -s /path/to/linked/file /path/to/new/file

It is important to fill this code with a complete path,
not a relative path from the current folder.
Hard links are created with the same command, without the -s
option. But hard links cannot link to directories and
cannot cross file system boundaries. (Does this mean one
cannot create a symbolic link to a removable drive?)
Symbolic links don't have these disadvantages, but they
are not updated if the source link is moved or removed.

<a href="https://www.cyberciti.biz/tips/understanding-unixlinux-symbolic-soft-and-hard-links.html">
Here</a> is  a reference which explains the differences between hard
and soft links, although the precise definition is quite difficult to
understand.

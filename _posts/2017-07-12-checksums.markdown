---
layout: post
title:  "Checksums"
date:   2017-07-12 13:00:00 -0200
categories: linux
---

We use checksums to make sure that a file was correctly downloaded,
especially large files, like isos. Or the Mathematica installation.
Linux Mint, for instance, provides the checksum for one of its installation
iso <a href="https://ftp.heanet.ie/mirrors/linuxmint.com/stable/18.2/sha256sum.txt">here</a>.

To check the integrity, you can run

    sha256sum -b ...iso

The option b reads the iso in binary mode. This is the first time I use this option and
it always worked, so I'm not sure what it did before. Or you may use the -c option
to read the sum from a file and check it. Try this:

    sha256sum --ignore-missing -c ...txt

Where the .txt file has a list of checksums. The option --ignore-missing tells the
program to ignore problems if some of the files are missing, because I downloaded only
one of the versions, not all of them.

Linux Mint, beginner friendly as always, provides a <a href="https://linuxmint.com/verify.php">
page</a> where this is throughly explained.

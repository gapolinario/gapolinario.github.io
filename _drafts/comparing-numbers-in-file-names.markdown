---
layout: post
title:  "Comparing numbers in file names"
date:   2019-11-15 14:00:00 -0200
categories: linux
---

This is a followup to the last post, where
we delete files by their names, this time
without regex, because everybody on
SE agree that regex is no good at comparing numbers,
it is made for text manipulation.

To retrieve the numbers in the names of files,

    ls | sed 's/p\([0-9]\+\).dat/\1/g'

Notice sed regex and perl regex are a little different.

Then I want to remove the file if the number is larger than 512, say.

    if [ 5 \> 8 ]; then echo "Yes"; else echo "No"; fi;

And this is how you run a conditional in bash

But this might need awk

    ls | gawk (print only the filenames matching pattern) | xargs -d"\n" rm

Below, prints if content of line is greater than 20,
what I want is to print if number within filename is greater
than 512.

    awk '{ a = $1; b = 20; print ( (a > b) ? $1 : "" )}' pt.dat
    awk '{ a = $1; print ( (a > 3) ? $1 : "" )}' pt.dat

replace all p*.dat with the string "AAA",
I don't know how to use awk variable

    awk '{gsub(/p([0-9]+).dat/,"AAA");}1' pt.dat

https://stackoverflow.com/questions/18179915/one-line-if-else-condition-in-linux-shell-scripting
http://mywiki.wooledge.org/ArithmeticExpression
https://stackoverflow.com/questions/18668556/comparing-numbers-in-bash


this was useful:

[ternary-print]: https://unix.stackexchange.com/questions/275198/awk-field-printing-within-the-ternary-operator

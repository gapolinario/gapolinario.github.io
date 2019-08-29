---
layout: post
title:  "Tracking Memory Use"
date:   2019-08-29 13:00:00 -0300
categories: linux
---

Several different ways to track memory and CPU use of commands on Linux:

The internal `time` command tracks rich information about processes

	usr/bin/time -v command

In the output, `resident set size` is equivalent to a measure of memory

There's also

	`ps -p <pid> -o %cpu,%mem,cmd`

but this does not display dynamical information, for this use `top`

	`top -p PID`

and with the code below, you can store all processes with `foo` or `bar` in
their name and run `top` only on these processes

	pids=( $(pgrep 'foo|bar') )

	top "${pids[@]/#/-p }"

Some references: [1][1], [2][2] and [3][3]

[1]: https://hackernoon.com/usr-bin-time-not-the-command-you-think-you-know-34ac03e55cc3
[2]: https://unix.stackexchange.com/a/414770/163964
[3]: https://unix.stackexchange.com/a/188706/163964
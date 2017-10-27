---
layout: post
title:  "Remote Logout"
date:   2017-07-14 12:00:00 -0200
categories: linux
---

I had a problem with a remote ssh session. A problem I still have to figure out how to solve:
at UFRJ I can log to CTG-dev and leave the computer logged for hours without touching it,
the connection is not lost. Here at home, if I connect to ssh, I have to always do something
at the terminal, or the connection is lost. I don't know if it's some configuration I can
fiddle with, or it is the fact that when at UFRJ the IPs are from the same place, and
that's why connection doesn't fall, I have to investigate that.

So the connection was lost and I was still connected, I logged in again and logged out of
the old session remotely, using:

    pkill -9 -t pts/9

First run 'tty', it shows what is your current session. Then run 'w', it shows all logged in user
sessions. When I didn't know that I used to run 'last' and it also showed the last sessions,
including the users logged in. 'w' is shorter and to the point.

Learned this <a href="https://superuser.com/questions/193168/how-can-i-logout-an-open-remote-ssh-session">
here</a>. StackExchange is always there for the solution.

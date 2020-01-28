---
layout: post
title:  "Remote Logout"
date:   2017-07-14 12:00:00 -0200
categories: linux
---

To log out of another session on the computer run

    pkill -9 -t pts/9

First run `tty`, it shows what is your current session. Then run `w`, it shows all logged in user
sessions. `last` can be used as well, it shows the last logged in sessions, including currently logged in users.

Learned this [here][super]

[super]: https://superuser.com/questions/193168/how-can-i-logout-an-open-remote-ssh-session

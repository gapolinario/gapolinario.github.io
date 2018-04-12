---
layout: post
title:  "How does anacron work"
date:   2017-06-18 13:00:00 -0200
categories: linux
---

Well, the file where the anacron configurations are stored is

/etc/anacrontab

And the file where the last time each job was run is in the folder

/var/spool/anacrontab

One can berify the execution status (though I still can't interpret it) with

grep cron.daily /var/log/syslog


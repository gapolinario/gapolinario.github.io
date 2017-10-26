---
layout: post
title:  "Scheduling tasks on Ubuntu"
date:   2017-06-18 12:00:00 -0200
categories: linux
---

Run 'crontab -e' to open the scheduling and add your jobs in the following format

    MIN HOUR DOM MON DOW CMD

These words mean:
MIN: minute
HOUR: hour
DOM: day of month
MON: month (from 1 to 12)
DOW: day of week (from 0 to 6, 0 is Sunday, on some systems it is 7)
And finally CMD is the command you want to execute at the established time.

Fill these fields with the appropriate numbers, or a * if the task is to be executed always, that is,
every minute, or every hour. You can use intervals too, like 09-18.

To view your crontabs, use 'crontab -l', this shows the crontabs for the user currently logged in.

You can else set up intervals for the task, thus `*/10` in the minute field means every 10 minutes.

There are also special keywords which can be used instead of the time assignment, they are: @yearly, @daily, @hourly, @monthly and @reboot.

Nice reference at [The Geek Stuff][geek].

[geek]: http://www.thegeekstuff.com/2009/06/15-practical-crontab-examples

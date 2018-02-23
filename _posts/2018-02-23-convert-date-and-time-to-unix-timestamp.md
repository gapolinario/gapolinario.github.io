---
layout: post
title:  "Convert date and time to UNIX timestamp"
date:   2018-02-23 11:00:00 -0200
categories: linux
---

I often use the [Alert Bot][alert] on Telegram,
it is very useful but when I need to send a message at a specific time,
I often use an approximate time.

To be more precise, run to a linux terminal and type

```Bash
date --date='02/25/2018 20:00:00' +"%s" | xclip -sel clip
```

This is going to convert the exact time and date you wish
to UNIX timestamp, and copies the result to
the clipboard,
then all you have to do is paste this timestamp
on the bot message.

[alert]: https://botsfortelegram.com/project/alert-bot/

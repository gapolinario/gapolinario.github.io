---
layout: post
title:  "BB on Linux: Updates"
date:   2017-11-05 13:00:00 -0200
categories: [linux, bb]
---

Following the tips from [this page][nimbus], I tried again to install
the BB security module.
First I removed `diagbb` package, which was installed in my previous tries,
and conflicts with `warsaw`.

Then I ran the following commands, on the Downloads folder
(notice the page has a small typo in the 64 bit section):

```
wget https://cloud.gastecnologia.com.br/bb/downloads/ws/warsaw_setup64.deb
sudo apt-get install libcurl3 libnss3-tools
sudo dpkg -i warsaw_setup64.deb
```

`warsaw` was successfully installed, but I can't find it in synaptic
or with `which`. I don't know how to show what version of it I am running.

The BB website shows how to test the installation of `warsaw.
Run

    ps -ef | grep warsaw

If there are two instances running, one as root and one as
the regular user, then the program is installed.
In my computer there were four instances.

But the website did not work on chrome, only on firefox.


[nimbus]: https://www.monolitonimbus.com.br/como-fazer-funcionar-os-sites-de-banco-no-linux/

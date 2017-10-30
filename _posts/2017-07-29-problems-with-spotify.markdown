---
layout: post
title:  "Problems with Spotify"
date:   2017-07-29 10:00:00 -0200
categories: [linux, spotify]
---

I had this problem where Spotify was always full screen, even hiding the taskbar, at the bottom
of the screen. I did some research and found [this][spotify] page reporting the
same problem. Although the OP says he had the problem using Windows 7, the accepted answer
has a strangely linux-looking format, it tells you to remove the "~/.config/spotify/window_position.prefs"
file, then open Spotify again. Indeed, it worked.

One more problem solved in Linux. I just don't know if the Spotify Windows user had his problem solved.

[spotify]: https://community.spotify.com/t5/Desktop-Linux-Windows-Web-Player/Spotify-open-in-full-screen-cannot-access-taskbar-anymore/td-p/1044311

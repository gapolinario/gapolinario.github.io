---
layout: post
title:  "How to cut a video with FFMPEG"
date:   2017-12-09 12:00:00 -0200
categories: [linux, video]
---

You can run

    ffmpeg -i movie.mp4 -ss 00:00:03 -t 00:00:08 -async 1 cut.mp4

`-t` defines an interval in the movie. `-to` would instead define an end time.

More details [here][se] and in the [official documentation][ffmpeg].

[se]: https://stackoverflow.com/questions/18444194/cutting-the-videos-based-on-start-and-end-time-using-ffmpeg
[ffmpeg]: https://ffmpeg.org/ffmpeg.html

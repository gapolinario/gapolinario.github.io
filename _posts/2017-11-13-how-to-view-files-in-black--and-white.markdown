---
layout: post
title:  "How to view files in Black & White"
date:   2017-11-13 13:00:00 -0200
categories: [linux, python]
---

To preview a file in black and white, all you need is imagemagick installed.
Run

```
convert source.jpg -colorspace Gray destination.jpg (true grayscale only)
convert source.jpg -monochrome destination.jpg (true black and white)
convert source.jpg -separate destination.jpg (separate into gray channels)
```

This works for pictures. For pdf files the quality is reduced much.

For a PDF

    gs -sOutputFile=output.pdf -sDEVICE=pdfwrite -sColorConversionStrategy=Gray -dProcessColorModel=/DeviceGray -dCompatibilityLevel=1.4 -dNOPAUSE -dBATCH input.pdf

If the output file is rotated, add `-dAutoRotatePages=/None`

According to comments, if you run this on a black and white original file, the
quality remains visually the same but the size of the file dramatically reduces,
this might be useful to reduce the size of large scanned notebooks.

Here are references on [imagemagick][fig-pb] and [gs][pdf-pb].

[fig-pb]: https://stackoverflow.com/questions/7708368/how-can-i-convert-an-image-to-grayscale-via-the-command-line
[pdf-pb]: https://superuser.com/questions/104656/convert-a-pdf-to-greyscale-on-the-command-line-in-floss

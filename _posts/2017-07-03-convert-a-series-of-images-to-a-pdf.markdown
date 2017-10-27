---
layout: post
title:  "Convert a series of images to a PDF"
date:   2017-07-03 13:00:00 -0200
categories: linux
---

If you just took a series of pictures, you can turn them into a single pdf very simply,
with the imagemagick program. If it is not installed, run


    sudo apt-get install imagemagick


Then, to convert the pictures, use

    convert image1.jpg image2.png image3.bmp output.pdf

This works with a number of extensions. In particular, if your pictures are named in series, like
page1, page2, page3, etc. You can try

    convert page*.jpg output.pdf



And it works just fine

More on this and a GUI way to do it at <a href="https://itsfoss.com/convert-multiple-images-pdf-ubuntu-1304/">How To Geek</a>.

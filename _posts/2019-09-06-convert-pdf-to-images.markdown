---
layout: post
title:  "Convert PDF to images"
date:   2019-09-06 10:00:00 -0300
categories: linux
---

`pdftoppm` is designed to convert PDF files to images in many possible formats

To convert a whole document, use

	pdftoppm input.pdf outputname -png

Each page is converted to an image and named as `outputname-x.png`, where `x`
is the page number.

For a single page

	pdftoppm input.pdf outputname -png -f {page} -singlefile

replacing `{page}` with a number, starting from one.

Several options for color, resolution and compression are available, see the `man` pages.
See more [here][ref].

[ref]: https://askubuntu.com/questions/50170/how-to-convert-pdf-to-image/50180#50180
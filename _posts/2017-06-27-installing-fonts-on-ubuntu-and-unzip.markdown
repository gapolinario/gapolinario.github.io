---
layout: post
title:  "Installing fonts on Ubuntu (and unzip)"
date:   2017-06-27 12:00:00 -0200
categories: linux
---

I downloaded a big file with fonts.
To install them, just throw everything in the `/usr/local/share/fonts/`
folder, with:

    sudo unzip fonts.zip -d /usr/local/share/fonts

This also illustrates how to unzip to a specific folder.

Good font collection can be found at [Typewolf][typewolf] and [Plato][plato].

The files in rar must be uncompressed with:

    sudo file-roller plato_fonts.rar

Open the compressed files manager with super user powers,
so you could extract the files to the proper directory.

To install the Plato Fonts collection, I tried

    sudo file-roller plato.rar -e /usr/local/share/fonts/

This returns a warning message, but in the end it works fine

[plato]: http://platowebdesign.com/articles/fonts/
[typewolf]: https://www.typewolf.com/google-fonts

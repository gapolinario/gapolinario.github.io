---
layout: post
title:  "Installing fonts on Ubuntu (and unzip)"
date:   2017-06-27 12:00:00 -0200
categories: linux
---

I downloaded a big file with fonts. An observation is that these font
compressed files are valuable, always keep them for future computers.
To install them, just throw everything in the /usr/local/share/fonts/
folder, like this:

    sudo unzip fonts.zip -d /usr/local/share/fonts

This also illustrates how to unzip to a specific folder.

The awesome font collection came from [Typewolf][typewolf].

Soon after that I tried to install the equally awesome package of
fonts from [Plato][plato],
but they are in rar format and I didn't know how to unrar from the terminal.
What I did was:

    sudo file-roller plato_fonts.rar

And I opened the compressed files manager with super user powers,
so I could extract the files to the proper directory.
After all this I was prepared to rock with my presentations.

But to install the Plato Fonts collection, this time I tried

    sudo file-roller plato.rar -e /usr/local/share/fonts/

This returns a warning message, but in the end it works fine

[plato]: http://platowebdesign.com/articles/fonts/
[typewolf]: https://www.typewolf.com/google-fonts

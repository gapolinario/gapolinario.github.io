---
layout: post
title:  "Default applications and xdg-mime"
date:   2017-11-14 18:00:00 -0200
categories: linux
---

If you want to know what is your default pdf reader,
just run

    xdg-mime query default application/pdf

`xdg-mime` is also used to set an application as default,
or to query the filetype. For instance

    xdg-mime query filetype blabla.jpg

Returns `image/jpeg`, this is a mimetipe and is
used as above to query the default application.

A list of mime-types is available [here][mime].

[mime]: https://www.freeformatter.com/mime-types-list.html

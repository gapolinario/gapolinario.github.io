---
layout: post
title:  "References on Latex Fonts"
date:   2017-07-26 12:00:00 -0200
categories: latex
---

On [this question][fonts] there is a table of fonts, font codes
(there is a specific name for this font coding, but
  I can't remember, this is very useful if you want
  to use any font that is installed on your computer) and some commands on
how to change the fonts for pieces of a document.

| Family                | Font Name | Sample      |
|:----------------------|:----------|:------------|
| pcr                   | Courier | <font face = "Courier">Lazy dog over the fence</font> |
| mdugm                 | Garamond | <font face = "Garamond">Lazy dog over the fence</font> |
| phv                   | Helvetica | <font face = "Helvetica">Lazy dog over the fence</font> |
| ptm                   | Times | <font face = "Times New Roman">Lazy dog over the fence</font> |

If you have to change the font of a specific extract of text,
but has to do it repeatedly, define the command:

    \newcommand*{\myfont}{\fontfamily{<familyname>}\selectfont}

And use it just like you use the `\bf` command:

    {\myfont ...}

If this is just a one time selection of a font, it is
not needed to define a command, just do

    {\fontfamily{<familyname>}\selectfont ...}

This is a trial to write in a different



[fonts]: https://tex.stackexchange.com/a/25251/107590

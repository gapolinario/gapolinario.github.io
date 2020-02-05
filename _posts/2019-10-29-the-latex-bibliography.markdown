---
layout: post
title:  "The Latex Bibliography"
date:   2019-10-29 15:00:00 -0300
categories: [science, latex]
---

In [this guide][bib],
the author  provides a handy guide to taking care
of your bibliographic entries in bibtex.

For instance, to keep capital letters properly in
the titles, remember to change them to sentence
case (manually), then preserve any proper names or acronyms
with the following regex:

	replace: \stitle={([\w\s-]*)}

	with: title={{$1}}

This replaces titles with single brackets with titles
surrounded by double braces. For instance,

	title={{Exact solution of a restricted Euler equation for the velocity gradient tensor}}

Would make the proper name Euler be displayed in lowercase,
while double braces preserve capitalization.

	title={{Exact solution of a restricted Euler equation for the velocity gradient tensor}}

This makes it all the more important to manually review the references for sentence case capitalization.

[bib]: https://serialmentor.com/blog/2015/10/2/Bibtex
---
layout: post
title:  "Convert Markdown to PDF"
date:   2018-03-02 12:00:00 -0200
categories: linux
---

To convert markdown documents to PDF, one has two options.

The first one is `pandoc`, with

```
pandoc input.md -o output.pdf
```

But this might present some issues.
For instance, long lines of code don't break
at the end of the page.

A better approach, some say, would be `gimli`,
though I was not able to install it on `ubuntu`.
---
layout: post
title:  "Vim: display colors of gnuplot"
date:   2017-06-26 12:00:00 -0200
categories: vim
---

I usually write my gnuplots files with a .gp extension and vim does not recognize it as gnuplot automatically.
To do so, one can type on vim


    :setf gnuplot



To change this permanently, add the following lines to your ~/.vimrc file:

```
" Set the type for the file type and override if file type
" already has detected
au BufRead,BufNewFile *.gp set filetype=gnuplot
```

To learn more, <a href="http://learnvimscriptthehardway.stevelosh.com/">this website</a> has many resources on vim scripts,
from customization (editing the ~/.vimrc file, like we just did), to more complex scripting and package building.

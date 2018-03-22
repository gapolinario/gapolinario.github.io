---
layout: post
title:  "Find the maximum of a column in a file"
date:   2017-06-19 12:00:00 -0200
categories: linux
---

I had a table of data and wanted to
find the maximum value of a column.
If your file is very large, unordered,
or both, this might help much,
in a terminal, run this command

```Bash
max=$(awk 'BEGIN{a=0}{if ($1>0+a) a=$1} END{print a}' mydata.dat)
```

And it returns on variable $max the maximum of column 1.
Then you can run

```Bash
grep -n $max my data.dat 
```

And this returns where in the file is that maximum entry

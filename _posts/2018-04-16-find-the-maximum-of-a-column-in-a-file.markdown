---
layout: post
title:  "Find the maximum of a column in a file"
date:   2018-04-16 16:00:00 -0200
categories: linux
---

I had a table of data and wanted to
find the maximum value of a column.
If your file is very large, unordered,
or both, this might help much.
In a terminal, run this command

```Bash
max=$(awk 'BEGIN{a=0}{if ($1>0+a) a=$1} END{print a}' mydata.dat)
```

Where `$1` means I want to find the maximum of column 1,
replace according to your needs.
This returns on variable $max the maximum of the column.
Then you can run

```Bash
grep -n $max my data.dat 
```

And this returns in what line of the file is that maximum entry.

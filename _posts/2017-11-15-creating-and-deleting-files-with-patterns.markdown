---
layout: post
title:  "Creating and deleting files with patterns"
date:   2017-11-15 12:00:00 -0200
categories: [linux, regex]
---

To create several files from `p1.dat` until `p1000.dat`:

    seq -f 'touch p%g.dat' 1 1 1000 | sh

You can count the number of files with

    ls | wc -l

Then I wanted to remove all files with a number larger than 512.
One can do this with a regex, first list all files:

    ls | grep -P "^p[1-9]\d{3,}|[6-9][0-9]\d|5[2-9]\d|51[3-9].dat"

The option `-P` means the pattern is a perl-regex.
This is experimental, according to the documentation,
the standard option would be `-e`, which is plain regex.

```
[1-9]\d{3,}    --> Matches all 4 or more digit numbers
[6-9][0-9]\d   --> Matches numbers between 600 and 999
5[2-9]\d       --> Matches numbers between 520 and 599
51[3-9]        --> Matches numbers between 513 and 519
```

Some further points to make clear:
1. `\d` matches any digit, it is the same as `[0-9]`
1. `\d{2}` matches any digit twice, and `\d{3,}` matches any digit three or more times.

The above command lists all files that will be deleted,
then pipes it to a remove command

    ls | grep -P "^p[1-9]\d{3,}|[6-9][0-9]\d|5[2-9]\d|51[3-9].dat" | xargs -d"\n" rm

This was a combination of three SE questions: To [create][create],
[match][match] and [delete][delete] with regex patterns.

There is the [Regex101][regex] website to test your regex.

But another alternative, simpler, would be to convert the string to
an integer and do a simple comparison in bash.
I still have to find out how to.

[create]: https://stackoverflow.com/questions/15813527/how-to-create-file-11-txt-22-txt-99-txt-with-regex
[match]: https://stackoverflow.com/questions/29977086/regex-how-can-i-match-all-numbers-greater-than-954/29977124#29977124
[delete]: https://superuser.com/questions/392872/delete-files-with-regular-expression
[regex]: https://regex101.com/

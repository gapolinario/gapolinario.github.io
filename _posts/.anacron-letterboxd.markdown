---
layout: post
title:  "Anacron and the Letterboxd watchlist"
date:   2018-01-08 12:00:00 -0200
categories: linux
---

See this for reference

https://serverfault.com/questions/99521/why-would-anacron-not-be-running

Guess what someone who is both a computerphile and a cinephile does?
Exactly, tracks its progress over the watchlist.

I created a file called `watchlist.py`

```Python
from datetime import date
import pandas as pd
import requests
import re

theList="/home/gabriel/Dropbox/Blog/Letterboxd/watchRecord.csv"
titles=['Date','Number']
page = requests.get('https://letterboxd.com/gapolinario/watchlist/')
match=re.search('to see (\d+)\&nbsp',page.text)
num=int(match.group(1))
watchRecord=pd.read_csv(theList,index_col=0)
today=pd.DataFrame([dict(zip(titles,[date.today(),num]))], columns=titles)
watchRecord=watchRecord.append(today,ignore_index=True)
watchRecord.style
watchRecord.to_csv(theList)
```

A file called `reset.sh` which creates a blank list

```Bash
#!/bin/bash

printf ",Date,Number\n" > watchRecord.csv
```

And another shell, `watchlist-sh` which calls the python code

```Bash
#!/bin/bash
python /home/gabriel/Dropbox/Blog/Letterboxd/watchlist.py
```

Then I copied this last script to the `/etc/cron.weekly` folder,
made it executable and it works.
This updates weekly, for those who don't watch movies so often,
one could change this to daily for debugging purposes or if one watches
movies frequently.

I tried typing this command directly on the file `/etc/anacrontab`,
but it didn't run, and I don't know why, still have not found out.

I still have not made code for visualizations.

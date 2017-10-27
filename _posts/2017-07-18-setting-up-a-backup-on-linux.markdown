---
layout: post
title:  "Setting up a backup on Linux"
date:   2017-07-26 12:00:00 -0200
categories: latex
---

An interesting option to backup a filesystem is


    rsync -av /home/ /media/backup_drive/



This is very similar to the command I use to send updates to this page.



a is archive, equivalent to -rlptgoD
r is recursive
l copies symlinks as symlinks
p is preserve permissions
t is preserve times
g is preserve group
o is preserver owner
n is a dry run, nothing really happens
--delete clears files that were deleted in the original folder, it doesn't acumulate
z is compress data



I added an alias to the ~/.bashrc file to make backup even easier. Just add the line:


    alias backup="rsync -av /home/ /media/gabriel/.../backup/ --delete"



Then all you have to do is run "backup" and the computer will do the task.
Remember to apply the changes to the bashrc with "source ~/.bashrc"
This can be made periodic with cron or anacron, maybe someday I will talk about it.

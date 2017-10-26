---
layout: post
title:  "Finding duplicate files"
date:   2017-06-19 12:00:00 -0200
categories: linux
---

`fdupes` is a powerful program that looks for duplicate files on your computer even if they have different names.
To search the folders Folder1, Folder2, etc for duplicate files, just run

    fdupes -r Folder1 Folder2 ... >> dupes.log

The output might be quite long, this is way I redirected it to a different file.
The program offers several options, like keeping only the first file and deleting all others,
or you can manually look at the log and decide what to do with the duplicated files.

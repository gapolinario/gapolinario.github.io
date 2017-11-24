---
layout: post
title:  "Convert music folder with ffmpeg"
date:   2017-11-17 12:00:00 -0200
categories: [linux, regex]
---

First, check whether the number of "points" is equal to the number of files

    ls | grep "." -c
    ls | wc -l

If they are equal, this means there are no files with crazy names and many points.
Proceed safely.

The following one liner converts all files in a folder
to mp3 format. Just navigate to that folder and run it.

    for i in *; do name=$(echo "$i" | sed 's/\.\w\+/\.mp3/'); ffmpeg -i "$i" "$name"; done

*I might add a $ to mean "end of file", maybe it is useful*

This is useful for compatibility reasons, not everybody can play an opus or ogg format.

And, you can get a list of formats of your files with

    ls | sed 's/[^.]\+\.\(\w\+\)/\1/' | uniq

This matches any ^. non dot character several times, then a dot, followed by word
characters and replaces the whole name of the file with just the extension.
`uniq` selects only unique entries in the file list. I don't know how this behaves
for filenames with more than one ".".

In the end, I have converted and would like to remove all files that are not of the desired extension, mp3 in this case, then run:

    ls | sed '/[^.]\+\.mp3/d' | xargs -d"\n" rm

For completeness, I did some research on which audio formats are lossy or lossless.
Lossy means the compression algorithm discards some data of the original file,
whereas lossless formats do not, albeit reduce the file to a manageable size.

Typical lossy formats are AAC, MP3 and WMA. And typical lossless formats are FLAC, WAV and ALAC.
The internet has several references, one of them is [this][lifewire].

[lifewire]: https://www.lifewire.com/what-makes-an-audio-format-lossless-2438560


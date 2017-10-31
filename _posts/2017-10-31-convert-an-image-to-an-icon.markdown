---
layout: post
title:  "Convert an image to an icon"
date:   2017-10-31 20:00:00 -0200
categories: linux
---

ImageMagick is the program behind the `convert` tool in linux.
I download an emoji from [EmojiOne][emoji] to use as a favicon for
this blog.

Then I learned about how to convert it to a favicon in [this thread][magick],
all you have to do is:

    convert -background transparent image.png -define icon:auto-resize=16,32,48,64,256 favicon.ico

And it creates the favicon in several sizes, because favicons are complicated
things. Then I moved the icon to the website main folder and it just worked.

[emoji]: https://www.emojione.com/
[magick]: https://unix.stackexchange.com/questions/89275/how-to-create-ico-file-with-more-then-one-image

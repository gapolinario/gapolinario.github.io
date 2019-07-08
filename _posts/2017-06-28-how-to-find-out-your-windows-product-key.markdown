---
layout: post
title:  "How to find out your windows product key"
date:   2017-06-28 12:00:00 -0200
categories: windows
---

A windows license is expensive and keeping your product key
is something you might need.
You can look it up under the computer (if it is a laptop),
usually close to the battery. But even if it has already
erased, you can find it out using the computer.

Open `Microsoft Powershell` and type

    (Get-WmiObject -query 'select * from SoftwareLicensingService').OA3xOriginalProductKey

If it doesn't work, there is software that does that, like ProduKey,
though I didn't try it. I also don't know what is the Powershell,
how it differs from Run and from the Command Prompt.

I found out about this at [How To Geek][windows].

[windows]: https://www.howtogeek.com/206329/how-to-find-your-lost-windows-or-office-product-keys/

---
layout: post
title:  "Report on Linux Mint 18.2"
date:   2017-07-14 13:00:00 -0200
categories: linux
---

After many years of continuous linux use and barely none of windows, with some problems in
the middle of the way, here I am with my first full installation of Linux on a computer.
It was a breeze and is flowing very well.

Antergos XFCE was very important in the customization process, as explained
in this [post][comp-names], with the history of my computers.
Then I installed
Ubuntu Gnome at UFRJ and had a problem with dual boot, both operating systems
are installed but it is very difficult to access windows, theoretically
I can enable secure boot and boot to windows, but I have never tried this.
And at home I tried to install virtualbox, and the graphics environment would
not work anymore after reboot. I tried some internet solutions, which did not
work. What worked was to backup my data on an external hard drive and
install Mint Cinnamon, that was when I decided to give up on windows.

The installation was done on wednesday, july 12. Then final customization was done
on thursday, july 13, and very quickly I had the computer up and running.

I had a strange problem, my screen was rotated when I turned on the computer.
Nothing happened on the test with the live usb, only when I turn on the computer for the
first time I saw the screen was rotated. Some incompatibility with my laptop which has
this rotating screen thing. The solution I found on the web was:

    gsettings set org.cinnamon.settings-daemon.peripherals.touchscreen orientation-lock  true

I don't know what it does, found it [here][rotate], and ever since my screen
has been correctly oriented. All updates work perfectly, and no spurious
problems have ever happened.

[rotate]: https://github.com/linuxmint/Cinnamon/issues/6059
[comp-names]: {% post_url 2017-08-17-old-computer-names %}

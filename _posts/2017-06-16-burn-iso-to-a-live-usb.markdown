---
layout: post
title:  "Burn ISO to a Live USB"
date:   2017-06-16 12:00:00 -0200
categories: linux
---

Download the .iso file, open a terminal and navigate to its folder, then run

    sudo -i

List the partitions on the computer

    lsblk


This will show you the name of the partition you want to format as a live USB and
tell you whether it is mounted or not. If it is, remember to unmount it

    umount /dev/sdb1

Then comes the burning part

    dd bs=4M if=myfile.iso of=/dev/sdb && sync


Notice this is not /sdb1/, but /sdb, simply. When you are done, don't forget to leave root

You may test the installation with a virtual machine, such as qemu. By running

    qemu-system-x86_64 -hda /dev/sdb


Finally, you can clean the USB drive with

    wipefs --all /dev/sdx

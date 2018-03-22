---
layout: post
title:  "Mount, unmount and format"
date:   2017-06-19 12:00:00 -0200
categories: linux
---

sudo mkdir /media/usb

lsblk

sudo mount /dev/sdb(1?) /media/usb/

sudo umount /media/usb/

sudo mkfs.vfat /dev/sdb1

or mkfs.ntfs or mkfs.ext4 
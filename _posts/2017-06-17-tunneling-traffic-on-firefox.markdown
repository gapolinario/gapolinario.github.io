---
layout: post
title:  "Tunneling traffic on Firefox"
date:   2017-06-17 12:00:00 -0200
categories: [linux, web]
---

How can I use Firefox as if I were in another computer?
You can log in to a remote computer

   ssh user@ip -D 1337

and `-D 1337` tells ssh to launch a SOCKS server on port 1337 locally.

Then open firefox, close all tabs, and go to Settings (the sandwich on the top right),
look for Preferences -> Advanced and, under Connection, go to Settings.

There, check 'Manual proxy configuration' and the line you need to change is SOCKS host:
change it to 'localhost' and port '1337'.

And you are done

Look up <a href="https://askubuntu.com/questions/469582/how-do-i-set-up-a-local-socks-proxy-that-tunnels-traffic-through-ssh">this question</a> for some details and more ssh options.

When you are done, go back to 'no proxy' on the Connection settings.

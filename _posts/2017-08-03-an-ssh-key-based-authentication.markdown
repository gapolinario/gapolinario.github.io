---
layout: post
title:  "An SSH key based authentication"
date:   2017-08-03 07:00:00 -0200
categories: linux
---

Set up a new key with

    ssh-keygen

Then provide a location (which might be just default) a passphrase to connect. The passphrase
is optional and
is only needed locally, this is one the reasons the key encription is more secure.
Then link this key to the remote server with

    ssh-copy-id username@remote_host

Done. You can connect to the remote server the same way as before, with

    ssh username@remote_host

This way you can access a remote host, or send files to a web server
without having to type your password every time. There is added security
because the local password might be simple, while the private key
is long and complicated, much more than is humanly possible.

To list all ssh keys configured in a computer and
check that you have associated the right keys, just run

    less ~/.ssh/authorized_keys

If you want more details and options, it is all explained in
<a href="https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server">
this article</a>.

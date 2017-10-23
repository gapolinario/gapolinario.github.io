---
layout: post
title:  "Configure Bitbucket to connect with an SSH key"
date:   2017-08-14 12:00:00 -0200
categories: git
---

Go to the settings on your Bitbucket account and add
the contents of the public key file,
~/.ssh/id_rsa.pub, for instance.
You can copy the contents of that file to the clipboard with

    cat ~/.ssh/id_rsa.pub | xclip -sel clip

Then change the {project-folder}/.git/config file.
Under the heading "remote origin", change the URL from https to ssh,
all the rest of the URL is the same. Apparently
this has to be done for each individual project.

Bitbucket has a great [tutorial][bit-ssh]
that explains all this in more detail. My approach in this text was very practical.

In Github, everything works in a similar fashion. Go to settings and add the contents of
the public key. You can clone the project directly with the SSH address and
everything works out of the box.

[bit-ssh]: https://confluence.atlassian.com/bitbucket/set-up-ssh-for-git-728138079.html

---
layout: post
title:  "How to Configure Mail on Ubuntu"
date:   2017-06-14 12:00:00 -0200
categories: [linux, mail]
---

First I had to install mailutils and ssmtp

    sudo apt-get install mailutils ssmtp

Then I changed the file /etc/ssmtp/ssmtp.conf,
after editing, it looks like this

```
# Config file for sSMTP sendmail
#
# The person who gets all mail for userids < 1000
# Make this empty to disable rewriting.
root=postmaster

# The place where the mail goes. The actual machine name is required no
# MX records are consulted. Commonly mailhosts are named mail.domain.com
mailhub=smtp.gmail.com:587
AuthUser=myemail@mail.com
AuthPass=mypassword
UseTLS=YES
UseSTARTTLS=YES

# Where will the mail seem to come from?
rewriteDomain=gmail.com

# The full hostname
hostname=computername

# Are users allowed to set their own From: address?
# YES - Allow the user to specify their own From: address
# NO - Use the system generated From: address
FromLineOverride=YES
```

Then emails are happily sent with

    printf "This is the message body\n" | mail -s "Topic" destinatario@mail.com

Apparently, hostname must be computer name, or it doesn't work.

For more on this take a look at
<a href="https://wiki.archlinux.org/index.php/SSMTP">ArchWiki</a>
or this
<a href="http://www.techrepublic.com/blog/it-security/use-ssmtp-to-send-e-mail-simply-and-securely/">
Tech Republic</a> article, which explains every line of configuration.

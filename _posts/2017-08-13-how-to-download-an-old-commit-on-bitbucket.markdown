---
layout: post
title:  "How to download an old commit on Bitbucket"
date:   2017-08-13 12:00:00 -0200
categories: git
---

I often have this problem, because I am not really skilled at Git, and because
I don't work at big projects, with many contributors. The solution I was looking
for is simply how to download a project as it was in an old commit.
This is pretty easy with Github, because the projects are publicly available, you
simply have to do this:


    wget https://github.com/{username}/{projectname}/archive/{sha}.zip



Then I wanted to do this for my bitbucket project.
There is a download link for each commit, but the projects are private, so we
have to authenticate. One does not have to type the password on
the command line, this is highly not recommended, for security reasons,
it is better to do the following:


    wget --user=username --ask-password https://bitbucket.org/{owner}/{repository}/get/{sha}.zip



All this was learned at StackOverflow: <a href="https://stackoverflow.com/questions/13636559/how-to-download-zip-from-github-for-a-particular-commit-sha">here</a> is the Git reference,
<a href="https://stackoverflow.com/questions/14528344/how-to-access-full-source-of-old-commit-in-bitbucket">
here</a> is the Bitbucket download link reference and
<a href="https://stackoverflow.com/questions/21236004/download-from-bitbucket-authorization-failed">
here</a> is the wget authentication reference.

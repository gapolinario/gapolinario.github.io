---
layout: post
title:  "Overwrite local files on Git Pull"
date:   2017-06-26 13:00:00 -0200
categories: git
---

First, a warning. The topic of this post refers to dangerous and not recommended practices. It refers to times
when I was less skilled at Git. Doesn't mean that nowadays I'm a git wizard, only means that I have learned
some safety practices since then.

Let's begin with the way I used to do it. When there was a merge conflict, I would simply erase the local
changes with

```
git fetch --all
git reset --hard origin/master
```

Of course I could only do it because I was the only one fiddling with the files and I knew which version was
the up to date one, and what changes I could discard. Then I learned some git (there's a codecademy course for
that, and numerous tutorials on the web). They showed me I should not pull, instead I should fetch and merge:

```
git fetch --all
git merge origin/master
```

or the lazy and somewhat dangerous version

    git fetch --all && git merge origin/master


I learned this [here][quora-git].

[quora-git]: https://www.quora.com/How-do-I-force-Git-to-overwrite-local-files-on-pull

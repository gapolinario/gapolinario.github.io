---
layout: post
title:  "Two Independent Branches on Git"
date:   2017-08-31 12:00:00 -0200
categories: git
---

I learned this to publish a github page.
The "master" branch holds the page, by default on github, this
can't be changed to gh-pages for free accounts, it seems, I must
check this.

To build the gh-pages branch, independent from the other branches, do:

```
git checkout --orphan gh-pages
git rm -rf .
echo "#Title of Readme" > README.md
git add README.md
git commit -a -m "Setting up gh-pages"
git push origin gh-pages
```

As explained
<a href="https://gist.github.com/seanbuscay/5877413">here</a> and
<a href="https://coderwall.com/p/0n3soa/create-a-disconnected-git-branch">here</a>.

On the command line, you can print what is the current branch with

    git branch | grep "*" | awk '{print $2}'

At least works for one-word branches, I did not test this for
more complex branch names.

You can delete a local branch with

    git branch -d <branch-name>

Then delete it on the remote with

    git push --delete origin <branch-name>

All branches can be quickly updated with

    git pull --all

Although this is only suitable for simple projects,
for more complex projects, this might cause problems
and conflicts

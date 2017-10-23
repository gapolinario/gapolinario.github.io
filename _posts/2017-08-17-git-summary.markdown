---
layout: post
title:  "Git summary"
date:   2017-08-17 12:00:00 -0200
categories: git
---

Still not revised. Badly not revised, by the way.

git add -A
git commit -m '<your message>'
git push origin master
Basic commands for pushing your commits from local computer to database

git push --force origin master
Force setting local as the default.

git pull origin master
Basic for pulling updates from remote to local computer



git checkout <commit> <file>
<file> is optional
revert <file> or whole folder to specified <commit>

git fetch
git reset

# puts local machine in sync with remote, cleans changes
git fetch --all
git reset --hard origin/master

git add -A
git commit -m 'Comment'
git push origin git

git pull origin master

git diff        # just like diff, show changes
git log         # show history of commits

git checkout stable     # change to branch stable
git merge new-idea      # merge branch new-idea into branch stable
git branch -d new-idea  # then you may delete branch new-idea, or continue working on it

say you have a flow like

M--N---------O--P--Q on branch master

run git branch dubious, then both master and dubious have the same tree structure
now run

git reset --hard <SHA1 sum of commit N>

then branch master has reverted to commit N and branch dubious still has the changes up to branch Q.

git fetch origin
git diff master origin/master       #show differences between remote and local
git merge origin/master             #merge imports

git show HEAD
git diff
git checkout HEAD file              #revert file back to HEAD (undo changes)
git reset HEAD file                 #unstage changes
git reset SHA                       # reset to a previous commit

git branch                          #show branches
git branch name                     # open a branch called name
git checkout name                   #go to branch name
git merge name                      #merge branch name with current working branch
git branch -d name                  #delete branch name

git clone remote_location clone_name    #make a copy
git fetch                           #brings changes to local branch
git merge origin/master             # merge local and remote
git push origin branche             #push commits in branch branche to remote

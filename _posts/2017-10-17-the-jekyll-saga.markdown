---
layout: post
title:  "The Jekyll saga"
date:   2017-10-17 12:00:00 -0200
categories: jekyll
---

The <a href="https://jekyllrb.com/">Jekyll website</a> has
full instalation instructions.
But first I had to install ruby-dev because of this
<a href="https://github.com/jekyll/jekyll-help/issues/209">error</a>,
which is related to the Ruby version in the Ubuntu repositories,
it seems.

    sudo apt-get install ruby-dev

After that, the gem install command worked just fine and I had
Jekyll installed.
Bundler is a program often mentioned, so it might be useful
to install it, do this with

    gem install jekyll bundler


Now you are ready to build your first Jekyll website, follow
their instructions, which is simply to run

    jekyll new myblog

This will create the myblog folder, you can preview this website
running

    bundle exec jekyll serve

And then navigating to [http://localhost:4000/][4000]
So far this is all, in the future there will be more on this adventure.

[4000]: http://localhost:4000/

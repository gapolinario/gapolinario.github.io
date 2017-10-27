---
layout: post
title:  "Film stills"
date:   2017-07-29 11:00:00 -0200
categories: references
---

This is just to save the place where I can find great film stills, of classic films,
arranged by title, director, and even cinematographer. The site is <a href="https://film-grab.com/">FilmGrab</a>

One more problem solved in Linux. I just don't know if the Spotify Windows user had his problem solved.

Recently the problem came back and was harder to solve, I had to delete both preference files,
one of which includes login data:

    rm ~/.config/spotify/prefs ~/.config/spotify/window_position.prefs

It works and resets standard configuration, but after that one has to log in again.
Maybe I can manually alter the prefs file to change window starting position,
and place it where I can minimize/maximize properly. Leave this to a later time.
Another solution is to only remove lines relative to window position, this is also something to try,
remember I have backups for both prefs and window_position, so that the situation can be reversed.

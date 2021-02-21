---
path: "/2013/12/02/updating-home-brew"
layout: post
title: "Updating Homebrew"
date: "2013-12-02T21:46:00.000Z"
comments: true
categories:
---

I was installing some dependencies for [PaulStretch](https://github.com/paulnasca/paulstretch_cpp) using
[Homebrew](http://brew.sh) and was getting download errors.
I thought that maybe Home Brew itself was out of date so I tried updating it and came across this error:

```bash
$ brew update
error: unable to unlink old '.gitignore' (Permission denied)
error: unable to unlink old 'README.md' (Permission denied)
error: unable to create file SUPPORTERS.md (Permission denied)
Checking out files: 100% (2135/2135), done.
Error: Failure while executing: git pull -q origin refs/heads/master:refs/remotes/origin/master
```

Turns out its easy enough to fix. I followed the instructions on Stack Overflow
[here](http://stackoverflow.com/questions/14113427/brew-update-failed)

Note: There is an edit about setting permissions towards the end of the top answer which I needed to follow as well, the original answer on its own was not enough.

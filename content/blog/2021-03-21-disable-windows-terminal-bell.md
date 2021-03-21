---
title: Disable Windows Terminal Bell
date: "2021-03-21T18:10:00.000Z"
---

How to turn off the Bell sound in Windows Terminal:
(Based on [this post](https://devblogs.microsoft.com/commandline/windows-terminal-preview-1-5-release/#audible-bell-%f0%9f%94%94) on the Windows Commandline Dev Blog)

Open Settings and under each profile you want to disable the bell for add `"bellstyle": "none"`

Not much else to say about it really, I use tab completion a lot in the terminal and it beeps at me every time so I wanted to turn it off. There's an old (and closed) StackOverflow question about it [here](https://stackoverflow.com/questions/36724209/disable-beep-in-wsl-terminal-on-windows-10) but all the responses involve customising your bashrc or equivalent.

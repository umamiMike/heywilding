---
date: 2020-12-10T18:22:27Z
description: "A helpful bit of kit when you need it"
draft: false
image: ""
title: "How to Use Tmux With Asciinema"
---

## what is asciinema?
It allows you to record and play back terminal sessions

## Why is it cool?

it is essentially screencapture without all the overhead of big files AND with added benefit that somebody can actively copy and paste from the screen recording, 

## What is tmux? 

Tmux allows you to create a custom set of windows, panes, and sessions.  If you use an ide like vscode or sublime, its like all the tool windows, but without all the overhead of other peoples biases about how you should use it.  I used vscode for a while, and I have a healthy set of vim commands.  There is a vim plugin for vscode BUT (as of when I last used it) the remapping is still bogus json files.

Anyhow, in TMUX you can run anything you want in any configuration you want.  It is as simple or as complicated as you make it based on how you work.

Note: this applies to terminal based applications.  You would use a "tiling" window manager if you want the browser and other applications handled. 

## Why would I use them together?

I want to record  multiple windows, I am often using tmux for doing reasonably complex tasks, or perhaps doing simple tasks in a complex way ;)

I love the compactness of asciinema vs recording a screencast video which will be in the many megabytes

I found some form of solution here if it is helpful -> 
[Recording a tmux session](https://github.com/asciinema/asciinema/wiki/Recording-tmux-session)

I wanted to write up the steps in a simple fashion, mostly so I have reference when  I need to do it.

### Steps:
1. start a tmux session, configure it how you like
2. detach from the session `<prefix+d>`
3. start asciinema recording
4. `tmux a`
5. do all your awesome recording 
6. detach again
7. stop the recording

Here is  an example in action, note I didnt futz with making a  perfect recording as illustration.

{{< asciinema MqpbJMDl2y75bD5CPSpLDn4QM >}}


---
published: true
title: "tmux session with multiple panes"
date: 16-02-2020
author: gitificial
description: "Scripts to open tmux sessions with multiple panes."
categories: [system, shell]
tags: [tmux]
---

<br/>

Working with the shell usually leads to more than one open terminal. But it's very tedious to open several terminals and bring them in place before you can start with your work. Fortunately the terminal multiplexer [tmux](https://tmux.github.io) allows you (beside other great features) to open multiple terminal sessions in a single window. And with a simple one-liner shell script you get the terminal arrangement you prefer. Here are just a few examples. At the very end you find a few useful keystrokes to handle a tmux session.


Tested with:

|-------------+-----------------|
| OS/Software |Version          |
|-------------|:----------------|
| Ubuntu      |18.04 LTS        |
| tmux        |2.6              |
|-------------+-----------------|

<br/>
### one pane left, two panes right
![12tmux](/assets/12tmux.png)

Create a executable shell script with the following content:
```bash
#!/bin/sh
tmux new-session \; split-window -h \; split-window -v \; attach
```

<br/>
### two panes left, two panes right
![4tmux](/assets/4tmux.png)

Create a executable shell script with the following content:
```bash
#!/bin/sh
tmux new -s '2x2 panes' \; split-window -h \; split-window -v \; select-pane -t 0 \; split-window -v \; attach
```


<br/>
### three panes left, three panes right
![6tmux](/assets/6tmux.png)

Create a executable shell script with the following content:
```bash
#!/bin/sh
tmux new-session \; split-window -p 66 \; select-pane -t 1 \; split-window -v \; select-pane -t 0 \; split-window -h \; select-pane -t 2 \; split-window -h \; select-pane -t 4 \; split-window -h \; select-pane -t 0
```

<br/>
### keystrokes

|----------------------+----------------------------------------|
| keystroke            |description                             |
|----------------------|:---------------------------------------|
| Ctrl-B cursor        |switch from one terminal to another     |
| Ctrl-B pg-up,-down   |scroll inside a terminal                |
| Ctrl-c               |leave selected mode (e.g. scrolling)    |
| Ctrl-B d             |exit tmux session*                      |
|----------------------+----------------------------------------|

*: To stop running tmux sessions, execute the following command:
```bash
$ tmux kill-session
```


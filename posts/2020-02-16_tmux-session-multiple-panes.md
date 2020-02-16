## tmux session with multiple panes
created: 16-02-2020

The terminal multiplexer [tmux](tmux.github.io) allows to open multiple terminal sessions in a single window. 


![12tmux](images/12tmux.png)

12tmux.sh
```bash
#!/bin/sh
tmux new-session \; split-window -h \; split-window -v \; attach
```

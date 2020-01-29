#### references  
https://man.openbsd.org/tmux.1

```
^b-h     help

^b:        enter command

tmux ls
tmux attach -t[term]
sessions
^b-s     list
^b-$     rename
^b-d     detach
^b-&     kill window

pane
^b-%     split vert
^b-“     split horiz
^b-x     close current
^b-q     show pane #
^b-o     next 
^b-;     prev
^b-arrow switch pane
^b-!     break out pane
^b-{     move pane left
^b-}     move pane right
^barrow  change pane
^b[alt-arrow]     resize pane

window
^b-c     create win
^b-n     next win
^b-p     pref win
^b-w     list
^b-,     rename
^b-[0-9] switch to win #

move window back/fwd  (^b :):
swap-window -t -
swap-window -t +

swap terminal 2 with 1:
swap-window -s 2 -t 1

bind it to a key where r allows repeat:
bind-key -r < swap-window -t -
bind-key -r > swap-window -t +

or bind to ctrl-shift left arrow:
bind-key -n C-S-Left  swap-window -t -1
bind-key -n C-S-Right swap-window -t +1

Atl-arrow to change window:
bind-key -n M-Left  select-window -t -
bind-key -n M-Right select-window -t +


^b-[     enter into buffer mode, pgup, pgdn

------------------------------------------------------
mouse
set -g mode-mouse on
set -g mouse-resize-pane on
set -g mouse-select-pane on
set -g mouse-select-window on
```

#### changed timeout for biding q for switching panes  
https://unix.stackexchange.com/questions/307696/how-to-increase-tmux-pane-numbers-display-time-ctrl-b-q  

in .tmux.conf  
```
set -g display-panes-time 5000
```

get cmd from tmux:  
binding :  




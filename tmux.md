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
^b arrow  change pane
^b[alt-arrow]     resize pane

window
^b-c     create win
^b-n     next win
^b-p     pref win
^b-w     list
^b-,     rename
^b-[0-9] switch to win #
^b pgup or ]  scroll (q to quit)

move window back/fwd  (^b :):
swap-window -t -
swap-window -t +

swap terminal 2 with 1:
swap-window -s 2 -t 1

swap current window with #
swap-window -t #

bind it to a key where r allows repeat:
bind-key -r < swap-window -t -
bind-key -r > swap-window -t +

or bind to ctrl-shift left arrow:
bind-key -n C-S-Left  swap-window -t -1
bind-key -n C-S-Right swap-window -t +1

Atl-arrow to change window:
bind-key -n M-Left  select-window -t -
bind-key -n M-Right select-window -t +

# copy
^b-[  - enter into copy mode, pgup, pgdn
arrow pgup/dn - to goto the start position
^-space - mark start position
arrow pgup/dn - to goto the end position
^-w - copy text to to tmux buffer
- switch to pane or file
^b ] - to paste tmux buffer

^b:show-buffer
^b:capture-pane
^b:list-buffers
^b:choose-buffer
^b:save-buffer file
^b:delete-buffer -b 1

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
set-option -g display-time 4000
```
display-panes-time - display when you show pane number 
display-time 4000 - display for status messages


get cmd from tmux:  
binding :  




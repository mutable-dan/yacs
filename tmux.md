## tmux ref

^b-h     help

^b:        enter command

tmux ls  
tmux attach -t[term]  
   
### sessions  
`^b-s`     list  
`^b-$`     rename  
`^b-d`     detach  
`^b-&`     kill window  
  
### pane  
`^b-%`     split vert  
`^b-“`     split horiz  
`^b-x`     close current  
`^b-q`     show pane #  
`^b-o`     next   
`^b-;`     prev  
`^b-arrow` switch pane  
`^b-!`     break out pane  
`^b-{`     move pane left  
`^b-}`     move pane right  
`^b arrow`  change pane  
`^b[alt-arrow]`     resize pane  
  
### layout  
`^b-<space>`    cycle layouts  

### window 
`^b-c`     create win  
`^b-n`     next win  
`^b-p`     pref win  
`^b-w`     list  
`^b-,`     rename  
`^b-[0-9]` switch to win #  
`^b pgup or ]`  scroll (q to quit)  
  
move window back/fwd  (^b :):  
swap-window -t -  
swap-window -t +  
  
swap terminal 2 with 1:  
swap-window -s 2 -t 1  
  
swap current window with #  
swap-window -t #  

move window  
move-window -t #  

also try `^b <` and `^b >`

  
bind it to a key where r allows repeat:  
bind-key -r < swap-window -t -  
bind-key -r > swap-window -t +  
  
or bind to ctrl-shift left arrow:  
`bind-key -n C-S-Left  swap-window -t -1`  
`bind-key -n C-S-Right swap-window -t +1`  
  
Atl-arrow to change window:  
`bind-key -n M-Left  select-window -t -`  
`bind-key -n M-Right select-window -t +`  

### copy  
```^b-[  - enter into copy mode, pgup, pgdn  ```
or ```^b alt pgup ```

arrow pgup/dn - to goto the start position  
^-space - mark start position  
^-w - copy text to to tmux buffer  
- switch to pane or file  
^b ] - to paste tmux buffer   

### buffer   
`^b:show-buffer`  
`^b:capture-pane`  ex. :capture-pane -S -, :capture-pane -S - -t 2, :capture-pane -a buffname -S -  
`^b:list-buffers`  
`^b:choose-buffer`  
`^b:save-buffer file`  
`^b:delete-buffer -b 1`  

#### search buffer 
```ctrl-r``` - reverse search  
```ctrl-s``` - forward search  
```shift-n``` - next  
   
example:  
`^b:capture-pane -S -`  
`^b:save-buffer <filename>`  
  
capture: - w/ no count get's all and puts into buffer  
save: save the buffer to a file  

------------------------------------------------------  
mouse  
set -g mode-mouse on  
set -g mouse-resize-pane on  
set -g mouse-select-pane on  
set -g mouse-select-window on  
  
#### changed timeout for biding q for switching panes    
https://unix.stackexchange.com/questions/307696/how-to-increase-tmux-pane-numbers-display-time-ctrl-b-q   
  
  
  
#### references   

https://man.openbsd.org/tmux.1  

.tmux.conf
```tmux
set -g display-panes-time 5000
set-option -g display-time 4000
set -sg escape-time 0
# use escape-time if pressing esc in vim and another key quickly is a problem

bind-key -n C-left select-window -t -
bind-key -n C-right select-window -t +

bind-key -n M-left select-pane -L
bind-key -n M-right select-pane -R
bind-key -n M-up select-pane -U
bind-key -n M-down select-pane -D

# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-resurrect'


# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

reload ```tmux source-file .tmux.conf```

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


^b-[     enter into buffer mode, pgup, pgdn


http://www.danielmiessler.com/study/tmux/

------------------------------------------------------
mouse
set -g mode-mouse on
set -g mouse-resize-pane on
set -g mouse-select-pane on
set -g mouse-select-window on

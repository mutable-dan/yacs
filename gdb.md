## gdb stuff
-tui

- ^x-1   2 win view
- ^x-2   3 win view
- ^x-o   change window

- ^x-s   single key mode
- ^l     refresh

### fork and exec
- set follow-fork-mode [same|new]
- set follow-exec-mode [parent|child]
catch exec

### source 
- set directories

### threads
- bt (backtrace)
- bt all threads
- thread apply all bt

### run with params
- gdb -tui --args app options < file
- or
- gdb> r -opt < file

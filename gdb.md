## gdb stuff

### in tui mode  ==> ^c-^a or gdb -tui

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

### using file for some project setting
file br 
===== set directories /home/user/dev/project
===== dir /home/user/dev/project/libs
===== dir /home/user/dev/project/db

where line 1 sets base project dir
lines 2,3 add source for libraries with debug

gdb> source br

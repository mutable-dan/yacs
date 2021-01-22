## gdb stuff

### in tui mode  ==> ^c-^a or gdb -tui

- ^x-1   2 win view
- ^x-2   3 win view
- ^x-o   change window

- ^x-s   single key mode
- ^l     refresh

### nav
n  
s  
fin  
c  [can do c n times]
r  
u n 
j  (set break after jump line)  j +- n, j n  
b
tb
b if expr
enable n
disable n
kill


### fork and exec
- set follow-fork-mode [same|new]
- set follow-exec-mode [parent|child]
catch exec
  
### source 
- set directories

### vars
- ptype
- p
- disp
- ser var =  

### info
- info args|local|frame|break|watch|var  
  
### frames
- bt (backtrace)
- f  
- f n
- up
- down  
### threads
- info threads
- thread #   -- switch thread
- break at thread #
- bt all threads
- apply gdb command to thread
-- thread apply [thread no|all] [command]  
-- thread apply all bt  
-- break 10 thread 2
  
### run with params
- gdb -tui --args app options < file
- or
- gdb> r -opt < file

### send ctrl-c to program
- signal SIGINT
  
### using file for some project setting where br is a break file
file br   
===== set directories /home/user/dev/project  
===== dir /home/user/dev/project/libs  
===== dir /home/user/dev/project/db  
  
where line 1 sets base project dir  
lines 2,3 add source for libraries with debug  

gdb> source br

#### info on shared libs
info sharedlibrary
see syms -> Yes/No if it has symbols
    Read if it has (*) with a not regarding debugging info
    
#### core
gcore [path] - core dump with verbosity



### set tty to other terminal
to send io to /dev/pts/10  
gdb> tty /dev/pts/10  


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
c  
r  
u  
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


### set tty to other terminal
to send io to /dev/pts/10  
gdb> tty /dev/pts/10  


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

#### debug on a thread 
- set scheduler-locking [off|on|replay|step]
  - off  any thread may run at any time 
  - on  only the current thread may run when 
  - step  single-stepping prevents other threads from preempting 
  - replay  off in record mode and like on in replay 
- set schedule-multiple  [on|off] 
  - on  all threads of all processes are allowed to run (i see as default to on despite the info in link below) 
  - off  only the threads of the current process are resumed 
    - but set non-stop on (default show non-stop off) 
https://sourceware.org/gdb/onlinedocs/gdb/Thread-Stops.html#Thread-Stops 

  
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


https://sourceware.org/gdb/onlinedocs/gdb/Forks.html

set follow-fork-mode mode 
 Set the debugger response to a program call of fork or vfork. A call to fork or vfork creates a new process 
 
show follow-fork-mode 
  Display the current debugger response to a fork or vfork call 
    
show detach-on-fork 
  Show whether detach-on-fork mode is on/off 

    


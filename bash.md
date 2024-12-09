some bash stuff

CDPATH -> defaults to .  

  
---------------
redirect stdout & stderr for all following  
 
#!/bin/bash  
exec &>> /out.log  
  
can also put in block  
{  
  ...  
} exec &>> /out.log  


--------------------  
key binding  
c-V then press key to get code  
so control-f10 is ^[[21;5~  
bind '"^[[21;5~": "echo helo"'  
or put bind "^[[21;5~": "echo helo" in .inputrc  


some alaises

alias l='ls -lh'
alias la='ls -al'
alias lh='ls -hl'
alias ltr='ls -ltr'
alias ..='cd ..'
alias p='pwd'
alias h='history'

alias df='df -h'

alias md='l && make debug'
alias mc='make clean'

alias lsblk='lsblk |grep -v snap'
alias p3='python3'

alias network-local-s='sudo arp-scan -l --resolve --format="${ip}\t${mac}\t${name}"'                                                             
alias netowrk-local='nmap -sP 192.168.0.1/24|grep -v Host'


alias shownetwork='nmap -sP 192.168.0.0/24|grep -v Host'
alias showaliases='cat ~/.bash_aliases'
alias editaliases='vim ~/.bash_aliases'


bind '"\e[A":history-search-backward'
bind '"\e[B":history-search-forward'

alias reload='source ~/.bash_aliases'

export PATH=$PATH:~/bin/:~/scripts/
export NO_COLOR=1




alias reload='source ~/.bash_aliases'  
---------------------------  
some key bindings  
bind '"\e[A":history-search-backward'  
bind '"\e[B":history-search-forward'  
     
type search letter(s) then up/down arrow   

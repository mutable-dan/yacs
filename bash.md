some bash stuff

CDPATH -> defaults to .  
bind '"\e[A":history-search-backward'  
bind '"\e[B":history-search-forward'  
  
  
  
alias l='ls -l'  
alias la='ls -al'  
alias lh='ls -hl'  
alias ltr='ls -ltr'  
alias ..='cd ..'  
alias p='pwd'  
alias h='history'  
  

alias lsblk='lsblk |grep -v snap'  
alias p3='python3'  
  
alias reload='source ~/.bash_aliases'  


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
c-v then press key to get code  
so control-f10 is ^[[21;5~  
bind '"^[[21;5~": echo "helo"'  
or put bind "^[[21;5~": echo "helo" in .inputrc  




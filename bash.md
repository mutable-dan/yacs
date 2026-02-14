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

### some alaises
```
alias l='ls -lh'
alias la='ls -alh'
alias lh='ls -hl'
alias ltr='ls -ltrh'
alias ..='cd ..'
alias p='pwd'
alias h='history'

alias df='df -h'

alias md='l && make debug'
alias mr='l && make release'
alias mc='make clean'

alias lsblk='lsblk |grep -v snap'
alias p3='python3'

alias show-network-s='sudo arp-scan -l --resolve --format="${ip}\t${mac}\t${name}"'
alias show-network='nmap -sP 192.168.0.1/24|grep -v Host'

alias showaliases='cat ~/.bash_aliases'
alias editaliases='vim ~/.bash_aliases'

#arduino
alias arduinoIde='firejail --ignore=noroot --ignore=no3d --appimage --private=$HOME/dev/arduino  ~/bin/arduino-ide_2.3.7_Linux_64bit.AppImage --no-sandbox'

alias myip='echo $(curl -s ifconfig.me)'

# fzf
alias fzfpv="fzf --preview 'cat {}'"
alias fzfbv="fzf --preview 'batcat --color=always {}'"


bind '"\e[A":history-search-backward'
bind '"\e[B":history-search-forward'

alias reload='source ~/.bash_aliases'

export PATH=$PATH:~/bin/:~/scripts/
export NO_COLOR=1
```

---------------------------  
some key bindings  
bind '"\e[A":history-search-backward'  
bind '"\e[B":history-search-forward'  
     
type search letter(s) then up/down arrow   

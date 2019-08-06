# vim 
### YACS - yet another cheat sheet

#### basic settings

Long form | short form | example
--------- | ---------- | -------
number|nu|set nu
tabstop|ts|set ts=3
expandtab|ex or et|set ex
autoindent|ai|set ai
smartindent|si|set si
shiftwidth|sw|set sw=3
nowrap|nowrap|set nowrap

example
```
:set nu ai et ts=3 sw=3 nowrap
```

#### misc

Description | example
----------- | -------
slit window|:sp
resize window|:res +5
move split|ctrl-w arrow or + -
no highlight|:noh

#### macros

Description | example
----------- | -------
record macro|q-a
end record|q
play|n@a  where option n is the number of repeats


#### Misc stuff

- fd - forward to char d
- G -end of file
- 22gg - line 22
- dtb - delete to char b
- ctA - change to A
- cc - change line
- % - brace match
- set showmatch

#### registers
Registers in Vim let you run actions or commands on text stored within them. To access a register, you type "a before a command, where a is the name of a register. If you want to copy the current line into register k, you can type

Show registers
:reg

Where k is the register name:
- "kyy  - yank line to register k
- "Kyy  - append to a register by using a capital letter
- "kp - past reg k
- "+y - copy to clipboard
- "+p - paste from system clipboard on Linux
- "*p - paste from "mouse highlight" clipboard on Linux

example: copy a word to reg a:
- v w "a y
- "a yw

#### paste into search line
copy as usual -->
^r"
or paste a reg ^rk
or ^r ^w

#### block select mode
- ^v  block select mode
- gv  reselect block
- v/   select to search term


#### markers
Description | example
----------- | -------
list marks|:marks
set marker to a|ma
goto a line of marker a|'a      
goto line and column of marker|`a      
next or prev mark line|]'  ['   
next or prev mark column|]  [`   
delete from cursor pos to marker|d'a    
delete marker a|delm a
del all markers|delmarks! 

Marker names
- a-z mark within file
- A-Z mark between files

# vim 
### YACS - yet another cheat sheet

Table|of|Contents
--------- | ---------- | -------
[Basic settings](#basic-settings)|[Misc](#misc)|[Macros](#macros)
[Move commands](#moving)|[Registers](#registers)|[Paste into line](#paste-into-search-line)
[Block select mode](#block-select-mode)|[Markers](#markers)|[Others CS](#Other-vim-cheat-sheets)|
[indent](#indent)|[ctags](#ctags)


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

#### additional settings
Long form | short form | example
--------- | ---------- | -------
cindent|ci|set ci
softtabstop|softtabstop|set softtabstop=3


example
```
:set nu ai et ts=3 sw=3 nowrap
```
#### indent

Description | example
----------- | -------
indent by shiftwidth|>>  <<
indent n lines by shiftwidth|n>> n<<
re-indent|==
re-indent n lines|n==
re-indent entire file|gg=G
indent on brace|>% <% =%
indent from marker|>'a

#### misc

Description | example
----------- | -------
slit window|:sp
resize window|:res +5
move split|ctrl-w arrow or + -
no highlight|:noh
undo|u
re-do|^r
repeat last cmd|.

#### macros

Description | example
----------- | -------
record macro|q-a
end record|q
play|n@a  where option n is the number of repeats


#### Moving

- fd - forward to char d
- Fd - backwards to char d
- G -end of file
- 22gg - line 22
- dtb - delete to char b
- ctA - change to A
- cc - change line
- % - brace match
- set showmatch
- ^o - go back prev position

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
next or prev mark column|```]`  [` ```
delete from cursor pos to marker|d'a    
delete marker a|delm a
del all markers|delmarks! 

Marker names
- a-z mark within file
- A-Z mark between files

#### ctags
- run ctags -R -> vim will see tag file 
- ^-] - find tag 
- ta - goto tag name 
- also ta, tn, tp 

#### Other vim cheat sheets

[vimsheet.com](http://vimsheet.com/ "vimsheet" )



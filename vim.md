# vim 
### YACS - yet another cheat sheet

Table|of|Contents
--------- | ---------- | -------
[Basic settings](#basic-settings)|[Misc](#misc)|[Macros](#macros)
[Move commands](#moving)|[Registers](#registers)|[Paste into line](#paste-into-search-line)
[Block select mode](#block-select-mode)|[Markers](#markers)|[Others CS](#Other-vim-cheat-sheets)|
[indent](#indent)|[ctags](#ctags)|[windows splits](#window-splits)|
[tabs](#tabs)|[Showchars](#showchar)|[Scroll Commands](#scrolling)
[Window move](#window-move)|[Range](#range)|[Sessions](#session)
[delete](#delete)



#### basic settings

Long form | short form | example
--------- | ---------- | -------
number|nu|set nu
tabstop|ts|set ts=3
expandtab|ex or et|set ex
noexpandtab|noex or noet|set noex
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

indent when pasting|cmd
-------|-----
no indent|set paste
normal|set nopaste

#### misc

Description | example
----------- | -------
split window|:sp
resize window|:res +5
move split|ctrl-w arrow or + -
no highlight|:noh
undo|u
re-do|^r
repeat last cmd|.
retab|:retab
open term|:term
set paste mode|:set paste 
unset paste mode|:set nopaste 

#### macros

Description | example
----------- | -------
record macro|q-a
end record|q
play|n@a  where option n is the number of repeats
:1,10norm! @a|Apply macro in reg a to lines 1-10
:%norm! @a|Apply macro in reg a to all lines
g/pattern/normal! @a|run macro a on all lines that match the pattern
let @a='ctrl-r ctrl-r a'|Paste current macro, put in .vimrc to save a macro


#### Moving

- w W b B e E - chars w/o a space
- ^ - firdt non blanch char
- g_ - last non blank char
- ctrl-d u - half page
- n% - % pos in file
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

#### scrolling
- z<t|z|b> top, middle, bottom
- z <cr> or zt -current line to top of page
- #z <cr> or zt - line # to top
- zz or z. - curren line to middle
- #zz or #z. - line # to middle
- z- or zb - current line to bottom
- #z- or #zb - line # to bottom
- [scrolling](https://unix.stackexchange.com/questions/110251/how-to-put-current-line-at-top-center-bottom-of-screen-in-vim)

#### registers
Registers in Vim let you run actions or commands on text stored within them. To access a register, you type "a before a command, where a is the name of a register. If you want to copy the current line into register k, you can type

Show registers
:reg

Where k is the register name:
- "ky  - yank line to register k
- "Ky  - append to a register by using a capital letter
- "kp - paste reg k
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
Insert with block mode 
 -  c-v 
 -  mv cursor  (down) 
 -  I 
 -  (enter text) 
 -  ESC 


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

#### Window splits
- `:sp` - split [file] - `^ws or ^wn`
- `:vs` - vsplit [file]  - `^wv`
- :help split
- `:close`
- `:ls` show files
- `:b #` open file in window
- `^w `arrow
- `^wn` next
- `^wp` prev
- `^wo` close all but
- `^wc` close 
- `^ww` toggle
- `^w j,k` (bottom, top), h,l (left, right)
- `^w(+-)`  resize (horiz) :resize +n|-n|n
- `^w(<>)` resize (virt)  :vert resize +n|-n|n
- `^w_`  zoom horizontal window
- `^w|`  zoom vertical window
- `^w=` equal size
- `#^w(+-)`
- `^w R`
- `^wHJKL ??`
- `^wr`
- `^wx`

 #### Window move
 - ^w window command mode
 - R window up/left
 - r window down/right
 - L window to far right
 - H window to far left
 - J window to top
 - K window to bottom
 - x ^x current window to closest to right
 - N leave terminal mode  (i to enter back into terminal mode)
 - :help window-moving
 
#### tabs
- :tabs
- :tabnew
- :tabn - next
- :tabp - prev
- :tabc - close
- :tabo - close all but
- :tabf
- :tabl
- :tabm [#]

#### range
:n,md delte lines . through m, where n or m can be . or $

#### delete
- dgg - delete from cursor to beginning 
- dG - delete from cursor to end 
- d0 or d^ - delete from cursor to start of line 
- d$ - delete from cursor to end of line 
- dta - delete forward until letter 'a' 
- dTa - delete backward until letter 'a' 

 #### session
 :wv [file]  - save viminfo to optional specified file
 :rv [file]  - restore viminfo
 :mks file   -  save session
 vim -S file
 

#### ctags
- run ctags -R -> vim will see tag file 
- ^-] - find tag 
- ta - goto tag name 
- also ta, tn, tp 

#### showchar
- :set list -> show control char, spaces and tab chars
- set listchars=tab:!·,trail:·,  -> custom chars


#### Other vim cheat sheets

[vimsheet.com](http://vimsheet.com/ "vimsheet" )  
[thevaluable.dev](https://thevaluable.dev/vim-advanced/")  


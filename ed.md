why ed?
3270 terminal emulator is line based.

**symbols**
```
* .         current line
* $         last line
* n         nth line fro 0 to $
* -         previous line
* ^n        nth previous line
* +         next line
* +n        nth next line
* ,         all lines 1 to $
* ;         current to last . to $
```


**command mode**
```
* q       quit
* Q       quit no save
* u       undo command
* w       save (can specify ne file name)
* [.,.]d  delete lines or current line
* [.,.]c  change lines or current line
* [.,.]j  join lines or current line
* i  insert before current line
* [.,.]m. move lines or current line to current
* [.,.tm. copy lines or current line to current
* [.,.]n  print lines or current line with line numbers
* [.,.]p  print lines or current line 
* [.,.]l  print lines or current line wait for neeline at end of page (don't do this w/ big files!)

* /text   search for text

```

**Example**
.,+22n  print 22 lines from current

**edit mode**
```
* .         leave
```


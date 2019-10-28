## Some commands for CP and CMS in z/VM

## Terminal
c3270 

## Info
[ibm ref: cp cms info!](https://www.ibm.com/support/knowledgecenter/SSB27U_6.4.0/com.ibm.zvm.v640.pdf/pdf.htm#zvmoper)

## io devices
* pun   punch
* ptr   printer
* rdr   reader
  
device id A -> personal

## cp 

* logon user here
* q userid
* q disk
* q v dasd
* q links

### from VM #cp q userid

acc id drive (associate id to drive)
  ex acc 191 a
  
term more a b
  lines and timeout
  
q rdr all
purge rdr all

  
## cms
ipl cms

### flist
```
flist a b c
  name type mode (drive)
  ex flist * exec a, flist, flist * * a
```

### from cp
- copy name type mode TO name type mode
- copy rhel kernel d kernel img a
- rename name type mod TO name type mode
- erase name type mod TO name type mode

### rename in flist
```
on line type
     rename / <F11>  a b =        rename file to a b and keep drive
     rename / a = =               rename file to a and keep 2ne and drive

  F11 clears to EOL
```
### copy and erase in flist
```
copy / a b =
erase <F11>  
```

### wipe v dasd
```
ickdsf
console
console

(for v dasd 100 w/ 65520 cyl)
cpvol FMT MODE(ESA) UNIT(100) VOLID(volid) NOVFY RANGE(0,65520)
u
end
```


## xedit
```
i  on the ===== put line belkow
d  on the ===== del line

====>
i
quit
qquit
file
save  
```

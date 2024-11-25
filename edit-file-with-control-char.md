### files with control chars   
how to search contents of filesystem and edit a file with unprintable control chars   
problem is, all files can look the same with the usual tools   
 
#### grep files show inode
```  grep -l "some search term" *|xargs -I {} ls -i '{}' ```  
   
sample output   
	600434  (unprintable chars)    
	600889   
	600987   
	601304   
   
#### edit file with inode 600434 in vim
```  find . -xdev -inum 600434 -exec vim {} \; ```

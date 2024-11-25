### files with control chars
 
#### grep files show inode
```  grep -l checkValidity *|xargs -I {} ls -i '{}' ```  
   
sample output   
	600434  (unprintable chars)    
	600889   
	600987   
	601304   
   
#### edit file with inode 600434 in vim
```  find . -xdev -inum 600434 -exec vim {} \; ```

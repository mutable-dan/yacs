find text in file ignoring hidden dirs: 
find . -type f -not -path "*/\.*" |xargs grep xyz

if using find with xargs and some files have spaces in the names, in order for it not to parse the name around spaces as files names:  
find . -name info -print0 |xargs -0 grep something  
or  
find . -name info -exec grep something '{}' +  

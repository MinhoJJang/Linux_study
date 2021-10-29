# IO Redirection_03

### Append

Basically, using __Standard Output__, if there are contents already in the file that you want to redirect the output, the original contents will be overwritten with new output. So, it maybe dangerous. 

If you want to **append**(Not Overwrite) the output of the execution, use like this:
```r
mhj@mhj-IdeaPad:~$ ls -l >> temp.txt
```

Then, the contents of the output will be redirected to the file by appending. 

### /dev/null

If you don't want to print the result of the command on the screen and save it to a file, use the following.
```r
mhj@mhj-IdeaPad:~$ ls -al > /dev/null
```
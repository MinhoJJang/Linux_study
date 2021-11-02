# SHELLSCRIPT_02

### /BIN

Let's find out shell's location in computer.
```r
mhj@mhj-IdeaPad:~$ ls /bin
```
This is a directory where programs that are basically mounted on Unix-based computers are located. There are _bash_, _zsh_, _echo_, _mv_, _pwd_, _ls_, _mkdir_... It means that all of the things we used as commands were actually files. And we are going to focus on _bash_.

### BASH SCRIPT

Let's make backup file with nano. If you are in nano editor, what we should do first is right this:
```
#!/bin/bash
```
When running this program called Backup, the operating system sees the symbol "#!" in the first line of the file called Backup. And after looking at the "bin/bash" after that, it can be seen that the codes written below them should be interpreted through a program called bash. This is a rule, a promise.

```
if ! [ -d bak ] ; then
    mkdir bak
fi
cp *.log bak
```
Does this command say that a directory named "bak" does not exist in the current directory? That's what "if ! [ -d bak ] ;" means. And If it does, "mkdir bak". And write "fi" at the end to inform the computer that the conditional sentence is over. So, we can now be sure that there is a directory called "bak" in the current directory. Then copy all of log files in current directory to "bak". And let's go out.

```
mhj@mhj-IdeaPad:~/script$ ls -l
합계 8
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 a.log
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 b.log
-rw-rw-r-- 1 mhj mhj   63 11월  2 11:40 backup
drwxrwxr-x 2 mhj mhj 4096 11월  2 11:00 bak
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 c.log
mhj@mhj-IdeaPad:~/script$ ./backup
bash: ./backup: 허가 거부
```
But we are failed to excute "backup". It's because somebody do not have permission to execute "backup". Therefore, in order to run that program, it is necessary to inform Linux that the file backup is executable.

```
mhj@mhj-IdeaPad:~/script$ chmod +x backup
mhj@mhj-IdeaPad:~/script$ ls -l
합계 8
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 a.log
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 b.log
-rwxrwxr-x 1 mhj mhj   63 11월  2 11:40 backup
drwxrwxr-x 2 mhj mhj 4096 11월  2 11:00 bak
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 c.log
```
Here, a difference before and after using the "chmod +x" command may be found. It is the very beginning of the backup file. In the newly changed state, 'x' is added, and 'x' means whether it is executable. That is, "chmod +x" means to change the mode to be executable.

> 1. When removing the bak directory and executing the backup file.
```
mhj@mhj-IdeaPad:~/script$ rm -rf bak
mhj@mhj-IdeaPad:~/script$ ls -l
합계 4
-rw-rw-r-- 1 mhj mhj  0 11월  2 10:59 a.log
-rw-rw-r-- 1 mhj mhj  0 11월  2 10:59 b.log
-rwxrwxr-x 1 mhj mhj 63 11월  2 11:40 backup
-rw-rw-r-- 1 mhj mhj  0 11월  2 10:59 c.log
mhj@mhj-IdeaPad:~/script$ ./backup
mhj@mhj-IdeaPad:~/script$ ls -l
합계 8
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 a.log
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 b.log
-rwxrwxr-x 1 mhj mhj   63 11월  2 11:40 backup
drwxrwxr-x 2 mhj mhj 4096 11월  2 11:51 bak
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 c.log
mhj@mhj-IdeaPad:~/script$ ls -l bak
합계 0
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:51 a.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:51 b.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:51 c.log
``` 

> 2. When the backup file is executed after partially removing the files inside the bak directory.
```
mhj@mhj-IdeaPad:~/script$ rm bak/a.log
mhj@mhj-IdeaPad:~/script$ ls -l bak
합계 0
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:51 b.log
mhj@mhj-IdeaPad:~/script$ ./backup
mhj@mhj-IdeaPad:~/script$ ls -l bak
합계 0
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:53 a.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:53 b.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:53 c.log
```


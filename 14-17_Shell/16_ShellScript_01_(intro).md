# SHELL SCRIPT_01

### Why we are using SHELL SCRIPT?

Before learning about _SHELL SCRIPT_, let's make temp files to study _SHELL SCRIPT_. But, this time, we don't using _SHELL SCRIPT_. Just Command one by one.
```r
mhj@mhj-IdeaPad:~$ mkdir script
mhj@mhj-IdeaPad:~$ cd script/
mhj@mhj-IdeaPad:~/script$ touch a.log b.log c.log

-> 'touch' makes files.

mhj@mhj-IdeaPad:~/script$ ls -l
합계 0
-rw-rw-r-- 1 mhj mhj 0 11월  2 10:59 a.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 10:59 b.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 10:59 c.log
mhj@mhj-IdeaPad:~/script$ mkdir bak
mhj@mhj-IdeaPad:~/script$ cp *.log bak 

-> * means all files that ends with '.log'. It is called 'wildcard'

mhj@mhj-IdeaPad:~/script$ ls -l bak
합계 0
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:00 a.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:00 b.log
-rw-rw-r-- 1 mhj mhj 0 11월  2 11:00 c.log
mhj@mhj-IdeaPad:~/script$ ls -l
합계 4
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 a.log
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 b.log
drwxrwxr-x 2 mhj mhj 4096 11월  2 11:00 bak
-rw-rw-r-- 1 mhj mhj    0 11월  2 10:59 c.log
mhj@mhj-IdeaPad:~/script$ cd bak
mhj@mhj-IdeaPad:~/script/bak$ ls
a.log  b.log  c.log
```
We will be able to sympathize with the reason for using shell scripts only if we assume that these commands occur very often. Let's find out in the next chapter.

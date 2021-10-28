# IO REDIRECTION_01

_IO_ is short for Input and Output, and _Redirection_ means re-direct something. So, redirect _WHAT_? Let's see.

### 1. Standard output

If you want to see what is in this directory, you will use this:
```r
mhj@mhj-IdeaPad:~$ ls -l
```
This command will show you a files and directories inside directory where you execute _ls -l_. But, if you want to save the result as a file, now you can use this:
```r
mhj@mhj-IdeaPad:~$ ls -l >result.txt
mhj@mhj-IdeaPad:~$ cat result.txt 
합계 56
...
```
'>' means _Redirection_ . And '>' has the same meaning as '1>'. Also, '>' is used when redirecting __Standard output__.

### 2. Standard error

Let's remove file. But if the file name is not right, the error will be printed, like this:
```r
mhj@mhj-IdeaPad:~$ rm rename2.txt
rm: 'rename2.txt'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
```
Then, how can we save this printed error as a file? It seems same as what we did before, but it has a small difference. 
```r
mhj@mhj-IdeaPad:~$ rm rename2.txt > errer.log
rm: 'rename2.txt'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
```
Error occurs. It's because '>' is used for redireting __Standard output__, not __Standard error__. So what we should use to redirect errors?
```r
mhj@mhj-IdeaPad:~$ rm rename2.txt 2> errer.log
mhj@mhj-IdeaPad:~$ cat errer.log
rm: 'rename2.txt'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
```
If you want to re-direct standard error, use '2>'. '2' means 'redirecting standard error'. 

### Applied Situation

Now you know two way to redirect the result of the command execution. So use both of them at once. Suppose 'A' is a command that you want to execute, and you want to redirect the result of execution to a file. Then you can use redirection like this:
```r
mhj@mhj-IdeaPad:~$ A 1> result.txt 2> error.log
mhj@mhj-IdeaPad:~$ cat error.log
A: 명령을 찾을 수 없습니다
```
If your execution has result, the result will be save to 'result.txt', and if your execution has an error, the error log will be save to 'error.log'. 
```r
mhj@mhj-IdeaPad:~$ ls -l
...
-rw-rw-r-- 1 mhj mhj    0 10월 27 23:29 result.txt
...
mhj@mhj-IdeaPad:~$ rm result.txt 1> re.txt 2> err.log
mhj@mhj-IdeaPad:~$ cat re.txt
mhj@mhj-IdeaPad:~$ cat err.log
mhj@mhj-IdeaPad:~$ ls -l
-rw-rw-r-- 1 mhj mhj    0 10월 27 23:32 err.log
-rw-rw-r-- 1 mhj mhj    0 10월 27 23:32 re.txt
```

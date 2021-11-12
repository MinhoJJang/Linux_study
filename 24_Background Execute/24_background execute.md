# Background execute 

When two or more windows are put up, the program I'm running in front of is called foreground, and the program I'm running behind is called background. We will find out how to move programs background and foreground.

## CTRL + Z 

Let's go into nano and make a hello.html file. At this time, if you save the file and press ctrl+z instead of going out to ctrl+x, it appears as follows.

```r
mhj@mhj-IdeaPad:~$ nano hello.html

나노로 돌아가려면 "fg"를 사용하십시오.

[1]+  Stopped                  nano hello.html
```
Here, fg stands for foreground. When fg is pressed in the above state, the nano editor appears on the screen. In other words, the nano editor is currently running in the background. 

Similarly, let's run the vim editor and press ctrl+z immediately. And when you execute the command _jobs_, it shows a list of programs currently running in the background.
```r
mhj@mhj-IdeaPad:~$ jobs
[1]-  Stopped                  nano hello.html
[2]+  Stopped                  vim
mhj@mhj-IdeaPad:~$ 
```
Here, '+' tells you what programs appear as fogrounds when fg is entered. And '-' means that when the program marked '+' ends, it comes out in the foreground.
```r
mhj@mhj-IdeaPad:~$ jobs
[1]   Stopped                  nano hello.html
[2]-  Stopped                  vim
[3]+  Stopped                  vi
```
Here, the preceding number helps specify the program you want to move to the foreground. For example, if you want to move program 1 to the foreground, write as follows.

```r
mhj@mhj-IdeaPad:~$ fg %1
```

If there is a program that you want to terminate in the background, use the following method. At this time, the kill-9 command is a forced end, and the kill command is a general (normal) end.

```r
mhj@mhj-IdeaPad:~$ jobs
[1]+  Stopped                  nano hello.html
[2]   Stopped                  vim
[3]-  Stopped                  vi
mhj@mhj-IdeaPad:~$ kill %2

[2]+  Stopped                  vim
mhj@mhj-IdeaPad:~$ jobs
[1]-  Stopped                  nano hello.html
[2]+  Stopped                  vim
[3]   Stopped                  vi
mhj@mhj-IdeaPad:~$ kill -9 %2

[2]+  Stopped                  vim
mhj@mhj-IdeaPad:~$ jobs
[1]-  Stopped                  nano hello.html
[2]+  Killed                   vim
[3]   Stopped                  vi
mhj@mhj-IdeaPad:~$ jobs
[1]+  Stopped                  nano hello.html
[3]   Stopped                  vi
``` 

## AMPERSAND(&)

The ls command shows all files and directories in the current directory. However, if the ls-R/ command is issued, it re-enters the internal directory as well as the files and directories in the current directory and recursively performs the ls command. Since it is difficult to find the result of this command in the console window, we will save this result using redirection.


```r
mhj@mhj-IdeaPad:~$ ls -alR / > result.txt 2> error.log
```

This shows that it takes quite some time, and if you assume that the time it takes is quite long, you will not be able to perform other commands during the time you execute the above command. In this case, when '&' is used, that command may be executed in the background. And if you enter jobs immediately, you can see what programs are currently running in the background.

```r
mhj@mhj-IdeaPad:~$ ls -alR / > result.txt 2> error.log &
[4] 17198
mhj@mhj-IdeaPad:~$ jobs
[1]+  Stopped                  nano hello.html
[3]   Stopped                  vi
[4]-  Running               ls --color=auto -alR /> result.txt 2> error.log &
```
And when this command is executed in the background, it sends a message called 'Exit 1'.

```r
mhj@mhj-IdeaPad:~$ jobs
[1]+  Stopped                  nano hello.html
[3]   Stopped                  vi
[4]-  Exit 1                ls --color=auto -alR / > result.txt 2> error.log
```

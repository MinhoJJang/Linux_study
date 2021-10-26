# CLI

## SEQUENCE EXECUTION (SEMICOLON)

We talk about GUI and CLI just before, and now we know CLI is more complicated than GUI, but CLI's usablity has much more potential than GUI. About its usablity, we talk about __sequence-execution__. Now let's see how it works in Linux.

### APPLICATION
Standard way to make directory and go into directory in console is right this:

```r
mhj@mhj-IdeaPad:~$ mkdir temp
mhj@mhj-IdeaPad:~$ cd temp
mhj@mhj-IdeaPad:~/temp$ 
mhj@mhj-IdeaPad:~$ rm -rf temp
```

It is not bad way, but it is the way that not using CLI's sequence-execution. So, what we gonna do? The answer is using **SEMICOLON**. Let's see.

```r
mhj@mhj-IdeaPad:~$ mkdir temp; cd temp
mhj@mhj-IdeaPad:~/temp$ pwd
/home/mhj/temp
```

Another way is this:

```r
mhj@mhj-IdeaPad:~$ mkdir temp2 && cd temp
mhj@mhj-IdeaPad:~/temp$ 
```

So, when will this be useful? If we don't know how long this command takes, then we don't need to wait for the previous command to execute next command.
# File find 02

## WHEREIS

It is a command to find the executable file.
```
mhj@mhj-IdeaPad:~$ whereis ls
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
```

|/usr/bin/ls|/usr/share/man/man1/ls.1.gz
|---|---|
The absolute path of the directory where the command _ls_ is located |The absolute path of the directory where the information that comes out when searched _man ls_ is located|

A question arises here. The command _ls_ is a file located under the bin directory. However, _ls_ can be executed in any directory. What's the reason? Let's find out the answer below.

## $PATH

$PATH is a variable, and the variable contains data. If you want to display the data on the screen, you can do it as follows.
```r
mhj@mhj-IdeaPad:~$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

This means that the data contained in the variable $PATH are output on the screen through echo.

If you look closely at that content, the information is classified through the colon, and these information based on each colon is a 'path'. Also, we have never created a variable called $PATH. In other words, this variable is basically what Linux has.

So, what are the values in this variable named PATH used for?

When we enter _ls_ at the terminal and enter, the operating system searches all the paths in this $PATH. If you find a program called _ls_ while exploring like that, you run it. And $PATH can be modified by the user. In other words, if we put the file we want into a specific directory and route it to #PATH, the computer can immediately find it when I run the file I want on the terminal. (That's why when installing java or gcc in a window environment, environmental variables were edited.) Therefore, when executing a command we want, there is a convenience that we do not have to write down the entire path of the directory where the command is located.

# IO REDIRECTION_02

### Program? Process?

Program and Process are seems simillar, but there are different. What we called "Program", typically mean the codes that in your SSD or HHD. And when the program is executed, we call it "Process". Even, one program can have multiple processes.

### Standard Input

Let's make temp file for testing. 
```r
mhj@mhj-IdeaPad:~$ nano temp.txt
```
Then, use this command:
```r
mhj@mhj-IdeaPad:~$ cat temp.txt
temp file
```
So, we can guess that _cat_ is showing something inside. (Actually _cat_ plays a role in combining multiple information.)

But, if you just enter "cat", something strange happens:
```r
mhj@mhj-IdeaPad:~$ cat
hi
hi
linux
linux
why r u copying me?
why r u copying me?
```
The command is just copying my **input**. It means, _cat_ recognize the data that the user's input as a **standard input**. So, _keyboard_ is basically a _standard input_. 

We just did redirecting something's output as a file. (Standard output & error) Let's think about it backwards. Then, we can redirect the contents of the file as a arguments of _cat_. How can we do this? Like this:
```r
mhj@mhj-IdeaPad:~$ cat < temp.txt 
temp file
```
_Cat_ basically get an input with using keyboard. But, by using **'<'**, _cat_ can get a file's contents as a input.

### What is difference?

```r
mhj@mhj-IdeaPad:~$ cat temp.txt
temp file
mhj@mhj-IdeaPad:~$ cat < temp.txt 
temp file
```
So, what is difference of two of them? It beacuse _cat_ has a two way of input. 

First, not using redirection, we using __Command Line Arguments__ as an input. So, ***cat temp.txt*** means __Command Line Arguments__.

 Second, _cat_ can also get input with __Standard Input__. So, by using ***<*** and gives a file name as a parameter, ***cat < temp.txt*** means not an argument, but a __Standard Input__. 

 ### IO Stream

```r
mhj@mhj-IdeaPad:~$ head linux.txt
```
This command prints basically up to ten paragraph of the file's content. But if you want to print just a part of it, use this:
```r
mhj@mhj-IdeaPad:~$ head -n1 linux.txt
```
-> -n(number of paragraph) 
As you might have expected, this command yields the same result as the following command.
```r
mhj@mhj-IdeaPad:~$ head -n1 < linux.txt
```

And if you want to save this output as a file, now you know, use this:
```r
mhj@mhj-IdeaPad:~$ head -n2 < linux.txt > part.txt
```
So, this command has a lot of meaning. It uses __Command Line Argument__, __Standard input__, and __Standard output__. The shape of the input and output flowing out is called __IO Stream__. 

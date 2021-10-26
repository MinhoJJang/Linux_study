# CLI

## PIPELINE

Pipelines are used to move something from A to B. This function is used in Linux, and it gives one command's result to another command's input. Now let's see how it works.

### GREP

First, let's make file, named 'linux.txt' by using nano editer. And just copy anything you want then paste it. 
```r
mhj@mhj-IdeaPad:~/temp$ nano linux.txt
```

If you want to check if the file is OK, use this:
```r
mhj@mhj-IdeaPad:~/temp$ cat linux.txt
```
You can see the every data of it. 

Then, If you want to print the line that has 'linux' in linux.txt, use __grep__. Like this:
```r
mhj@mhj-IdeaPad:~/temp$ grep linux linux.txt
```
Then you can see the sentences that has 'linux' in it.


### PIPE 

So, let's use it in the applied situation. When we want to know about the command, we use this:
```r
mhj@mhj-IdeaPad:~/temp$ ls --help
```
but it is so complicate that we can't find word that we want to use. In this case, we can use both __grep__ and __pipe__ to found useful data.
```r
mhj@mhj-IdeaPad:~/temp$ ls --help | grep sort
# pipe is this: |
```
Pipe can be connected for several times, so you can use pipe like this:
```r
mhj@mhj-IdeaPad:~/temp$ ls --help | grep sort | grep file
  -S                         sort by file size, largest first
```

### APPLICATION OF PIPE & GREP

```r
mhj@mhj-IdeaPad:~/temp$ ps aux
```
It shows every process in your computer. If you want to found specific named process, use this:
```r
mhj@mhj-IdeaPad:~/temp$ ps aux | grep vscode
```

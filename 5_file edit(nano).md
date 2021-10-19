# file editer

File is most basically method that save informations, like storage. And directory is used to orgainize files.

In Linux, there are two file editers, **nano** for linux beginners, and **vi** for over linux intermediaters. So, we are going to learn about _nano_. 

# nano

To go inside _nano_, just type _nano_ and enter. 
There are so many commands to use _nano_, let me know about basically used commands. 

## ^( ), M-( )

__^__ means __ctrl__, and __M-__ means __alt__. 

### ^O , ^C
First, to name files that you make with _nano_, __^O__ command will let you naming your file. And there are also such a commands that you can use, if you type __^C__, _nano_ cancels your behavior that you did it just before. 

### ^X , ^Z

- __^X__ means __Exit__, and it can also save your files if you enter __y__. 

- __^Z__ command is immediately exit from your file, and you can go back to it if you enter __fg__ before you go out from Console. 

### M-U , M-E

- __M-U__ : Undo
- __M-E__ : Redo

### ^K , ^U, ^6, ^W

let me make example to explain these commands... named _nano.html_

```html
<html>
    <body>
        Hello
        nano
    </body>
</html>
```

If you want to cut everything in a line that cursor exists, enter __^K__. and move your cursor to where you want to paste it, and just enter __^U__. 

But if you want to copy(do not cut everyting in a line), move your cursor front where you want to start copy. Then press ^6, mode will be changed to __Mark Set__. Then move cursor with arrow_keys and stop where you want to stop. And then __^K__, then move your cursor where you want to paste it, then __^U__.  

If you want to find word in file, press __^W__ and enter word that you want to find. 

### ^G 

__^G__ commmand that help you to find commands or explanations about _nano_. Use it and become experienced! 

P.S : Well, After you become experienced about __nano__, I recommed you to use __vi__. 
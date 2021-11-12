# File find 01

Files are largely classified into two uses: the first is the file for storing data, and the second is the executable file for storing commands for what to do. Whatever the purpose of the file is, let's find out how to locate the file.

## Locate

```
mhj@mhj-IdeaPad:~$ locate *.log
```
This way, it shows the log file existing on the database. At this time, it should be noted that the location command does not search the directory one by one. The database is a space in which information is stored, and the information contains information on files stored in this computer. The database is named __mlocate__ and stores various information about files on this computer through a task called ***sudo updatedb***. This task is set to operate once a day on a Linux system. That is, since files are found in this organized database, files can be imported much faster.

## Find

If you take this link, you can see 35 types of find usage.          
[FindUsage](https://www.tecmint.com/35-practical-examples-of-linux-find-command/)            
Let's find out a few of these uses.

### Find Files Using Name in Current Directory
```
# find . -name tecmint.txt
./tecmint.txt
mhj@mhj-IdeaPad:~$ find ~ -name *.log
```
To explain each keyword here, it is good to understand as follows.

keyword|#|.|~|-name|*.log
|------|---|---|---|---|---|
|explanation|Route Permission|Means to find the directory below the current directory|It means that I will find the home directory first|It means finding a file through the file name|It means that you will find all the files that end in .log.
|

### Find and remove single File
```
# find . -type f -name "tecmint.txt" -exec rm -f {} \;
```
keyword|-type|f|-exec|rm -f|{}|
|------|---|---|---|---|---|
|explanation|Specify the type of file you're looking for|Meaning you're going to find only the file type|Meaning you're going to execute the following command|Meaning you're going to delete the file immediately without any warning when you delete it|Place where the name of the file you searched through the command is located|

In other words, this is a strong command to delete the searched file.

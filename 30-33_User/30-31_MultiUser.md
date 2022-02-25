# MultiUser

The multi-user function is generally not well used at the moment. Let's just catch on to this and get a quick look.

# id

```
mhj@mhj-IdeaPad:~$ id
uid=1000(mhj) gid=1000(mhj) 그룹들=1000(mhj),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),121(lpadmin),131(lxd),132(sambashare)
```
 
When you type id, it tells you who is currently connected, and you can see that the user is connected to a group called 'mhj'.

# who

```
mhj@mhj-IdeaPad:~$ who
mhj      :0           2022-02-25 19:00 (:0)
```

In the case of who, it is an order to tell who is currently connected. Because I'm the only one who's currently logged on, only one person comes out like that.

If there are several people who have accessed, in the case of an id command, information of a **current** person will be visible, and in the case of a who command, information of **all** people who have accessed will be visible.
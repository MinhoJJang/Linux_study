# RootUser

There are two users in the Unix family. One is a Super (Root) User, and the other is a general user. The representative command used for Root User authority is 'sudo'. For example, a command such as 'sudoapt update-y' may be temporarily received from the superuser to perform the command.

However, this is a temporary order because it becomes a super user only for one moment. Then, what is the way to become a super user?

First of all, before becoming a super user, you have to know whether you are a regular user or a super user. Then you can look at the basic message output on the bash.

```
mhj@mhj-IdeaPad:~$
```

As such, the general user has a custom name in front of '@'. On the other hand, super users have a content called 'root' in front of '@'. In addition, the last '$' mark means that this user is currently a general user. If you are a super user, a '#' mark will appear.

|User|SuperUser|
|-|-|-|
|front of @|customName@~|root@~|
|기호 표시|$|#|

To become a super user in the Unix series, 'su' can be used. If the password of the super user is not set in ubuntu, the password can be set first through the 'su-root' command, and then enter the super user's authority with the 'su-root' command.

```
mhj@mhj-IdeaPad:~$ su - root
암호: 
root@mhj-IdeaPad:~# exit
로그아웃
mhj@mhj-IdeaPad:~$
```

However, since superusers have strong authority, responsibilities follow according to authority. Therefore, it can be said that it is the right way to use strong commands using 'sudo' only when necessary, which is usually used as a general user.
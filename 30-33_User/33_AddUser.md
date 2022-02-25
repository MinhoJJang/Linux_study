# AddUser

This time, let's find out how to add users to your computer.
## useradd  

In order to add a user, a command called 'useradd-m' is required. Naturally, it is impossible for ordinary users to add regular users, so they are added using administrator authority.

```r
mhj@mhj-IdeaPad:~$ sudo useradd -m testUser
[sudo] mhj의 암호:
mhj@mhj-IdeaPad:~$ cd /home
mhj@mhj-IdeaPad:/home$ ls
hdd  mhj  newhdd  testUser
```

In this way, it can be seen that a user named testUser has been added to the home directory.

However, if you try to log in as that user, the following error occurs.

```r
mhj@mhj-IdeaPad:/home$ su - testUser
암호:
su: 인증 실패
```

What's wrong? We made an ID, but we can't log in because we've never made a password. Then let's set up the password.

```r
mhj@mhj-IdeaPad:/home$ sudo passwd testUser
새  암호:
새  암호 재입력:
passwd: 암호를 성공적으로 업데이트했습니다
```
 
And when you log in, you log in normally.

```r
mhj@mhj-IdeaPad:~$ su - testUser
암호:
$
```

## To be RootUser

But what if the testUser wants to use the sudo command? Let's see what happens when we give the sudo command in this state.

```r
mhj@mhj-IdeaPad:~$ su - testUser
암호:
$ sudo pwd
[sudo] testUser의 암호:
testUser은(는) sudoers 설정 파일에 없습니다.  이 시도를 보고합니다.
```

As such, the testUser does not exist in the sudoers file, so the sudo command cannot be written.

Then, what should I do to give this user Rootuser authority?

If you think about it a little bit, you will see that only super users can give super users authority. Therefore, you can enter the superuser who can use the sudo command and give the testUser the Rootuser authority.

```r
mhj@mhj-IdeaPad:~$ sudo usermod -a -G sudo testUser
```

|-a|-G|
|-|-|
|-a, --append|-G, --groups GROUP1[,GROUP2,...[,GROUPN]]]|
|Add the user to the supplementary group(s). Use only with the -G option.|A list of supplementary groups which the user is also a member of. Each group is separated from the next by a comma, with no intervening whitespace. The groups are subject to the same restrictions as the group given with the -g option. If the user is currently a member of a group which is not listed, the user will be removed from the group. This behaviour can be changed via the -a option, which appends the user to the current supplementary group list.|

Since the testUser was made RootUser through this command, the sudo command shows that it is operating normally.

```r
mhj@mhj-IdeaPad:~$ su - testUser
암호:
$ sudo pwd
[sudo] testUser의 암호:
/home/testUser
```







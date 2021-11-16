# Daemon_02

Now let's find out what daemons are by installing and running our own programs.

## Service 
Let's install apache2, a representative web server among web servers.

```
mhj@mhj-IdeaPad:~$ sudo apt install apache2
```
So where is this installed apache2? Let's move as below.

```
mhj@mhj-IdeaPad:/etc/init.d$ ls
acpid                dbus               procps
alsa-utils           gdm3               pulseaudio-enable-autospawn
anacron              gdomap             rsync
apache-htcacheclean  grub-common        rsyslog
apache2   
...etc
```
In this way, it can be seen that a web server called apache2 is installed in a place called __/etc/init.d/___. This directory is where daemon programs are located. That is, programs with the purpose of daemon are located in this directory. Also, the programs here are different from the way we generally turn on and off programs.

```
mhj@mhj-IdeaPad:/etc/init.d$ sudo service apache2 start
```
Since these programs are services, they add the keyword service to the front and the keyword start to the end. Then, did that service really run? So check it out.

```
mhj@mhj-IdeaPad:/etc/init.d$ ps aux | grep apache2
root        9862  0.0  0.0   6532  4572 ?        Ss   15:06   0:00 /usr/sbin/apache2 -k start
www-data    9863  0.0  0.0 1997852 4604 ?        Sl   15:06   0:00 /usr/sbin/apache2 -k start
www-data    9864  0.0  0.0 1997852 4604 ?        Sl   15:06   0:00 /usr/sbin/apache2 -k start
mhj        11619  0.0  0.0  10360   732 pts/0    S+   15:15   0:00 grep --color=auto apache2
```
Then, what if you want to turn off this executed service? You can do it as below.
```
mhj@mhj-IdeaPad:/etc/init.d$ sudo service apache2 stop
mhj@mhj-IdeaPad:/etc/init.d$ ps aux | grep apache2
mhj        11960  0.0  0.0  10360   736 pts/0    S+   15:17   0:00 grep --color=auto apache2
```
You can turn on and off the service like this. And all programs executed with the service keyword essentially have a common command of start and stop. So general programs can just be executed, but programs corresponding to daemons must be bypassed through a program called a service to start and stop.

## Auto Start

The daemon programs identified above need to be automatically turned on when the computer runs. In that case, what should I do?

```
mhj@mhj-IdeaPad:/etc/init.d$ cd ..
mhj@mhj-IdeaPad:/etc$ cd r
rc0.d/     rc2.d/     rc4.d/     rc6.d/     rsyslog.d/
rc1.d/     rc3.d/     rc5.d/     rcS.d/
``` 
Among them, if the operating system is running with the CLI, enter rc3.d/, and if the operating system is running with the GUI, enter rc5.d/.

```
mhj@mhj-IdeaPad:/etc$ cd rc3.d/
mhj@mhj-IdeaPad:/etc/rc3.d$ ls -l
합계 0
lrwxrwxrwx 1 root root 29 11월 16 15:06 K01apache-htcacheclean -> ../init.d/apache-htcacheclean
lrwxrwxrwx 1 root root 16 10월 20 22:52 K01gdomap -> ../init.d/gdomap
lrwxrwxrwx 1 root root 27 10월 20 23:04 K01speech-dispatcher -> ../init.d/speech-dispatcher
lrwxrwxrwx 1 root root 15 10월 20 22:52 S01acpid -> ../init.d/acpid
lrwxrwxrwx 1 root root 17 10월 20 22:52 S01anacron -> ../init.d/anacron
lrwxrwxrwx 1 root root 17 11월 16 15:06 S01apache2 -> ../init.d/apache2
...etc
```
You can find a program called apache2 here, and in front of it is the name S01apache2. This name is called 'Link', and the actual program is located in the name of.../init.d/apache2, but the link is named S01apache2. In other words, in terms of windows, you can think of it as a shortcut or simply hanging a name. Let's find out what this means in detail below.

```
mhj@mhj-IdeaPad:/etc/rc3.d$ ./S01apache2
Usage: apache2 {start|stop|graceful-stop|restart|reload|force-reload}
```
The link runs in this way. In reality, the program is not located in this directory, but it would be easy to think that it acts as if there was a program called apache2.

In addition, if this link starts with S and is in the directory rc3.d/, it means that it is a program that runs automatically when it is a computer booted to the CLI. On the other hand, if the link name starts with K, it means that even if the computer boots in the CLI method, it will not run. In addition, the numbers '01' and '02' in the links named S01 to S02 mean priority.

To summarize the above in a simple table, it is as follows.

|S01apache2|S|01|
|----------|-|--|
|The actual program is located in '../init.d/apache2', but the link is named 'S01apache2'. It's comfortable to think of it as a shortcut.|In the case of S, a program that runs when the computer boots, and in the case of K, it does not run when it boots.
|In the case of numbers such as 01,02, it means the operation priority of the program.|

Anyway, if we want a daemon program to run automatically when the computer boots, we can link it to a directory called etc/rc3.d/ with a name similar to S01apache2.
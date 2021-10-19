# what is package?

We already use a lot of packages... even __ls__, __mkdir__ is a package! But it is basically built-in pakages. So we are going to learn about package manager, which can manager files. 

There is two typical package manager, __apt__ , __yum__. Now we are going to learn __apt__. 

# apt

To see what we can do with _apt_, just type _apt --help_ or _apt -h_. Then you can see a lot of commands what you can do with _apt_. 

```r
mhj@mhj-ideapad:~$ apt --help
apt 2.0.6 (amd64)
Usage: apt [options] command

apt is a commandline package manager and provides commands for
searching and managing as well as querying information about packages.
It provides the same functionality as the specialized APT tools,
like apt-get and apt-cache, but enables options more suitable for
interactive use by default.

Most used commands:
  list - list packages based on package names
  search - search in package descriptions
  show - show package details
  install - install packages
  reinstall - reinstall packages
  remove - remove packages
  autoremove - Remove automatically all unused packages
  update - update list of available packages
  upgrade - upgrade the system by installing/upgrading packages
  full-upgrade - upgrade the system by removing/installing/upgrading packages
  edit-sources - edit the source information file
  satisfy - satisfy dependency strings
```

And very Important thing is that you **should be a root** before using _apt_. So there are two typical way to be a root. First, type _sudo_ after command that you want to execute. Second, type _sudo su_, and become a root.
If you become a root, there will be __#__ instead of __$__. 

If you want to escape from root, just type __exit__ or __ctrl+d__. This command is available not only escaping from root, but also escaping from Console command or Terminal.

```r
mhj@mhj-ideapad:~$ sudo su
root@mhj-ideapad:/home/mhj# 
```

### apt-get update (...)

This command downloads the **lists** of your software up-to-date. (It downloads lists! Not softwares.) If you just type _apt-get update_, it updates everything that you installed softwares via _apt-get_.
```r
mhj@mhj-ideapad:~$ sudo apt-get update
Hit:1 http://mirror.kakao.com/ubuntu focal InRelease
Hit:2 http://mirror.kakao.com/ubuntu focal-updates InRelease                 
Hit:3 http://mirror.kakao.com/ubuntu focal-backports InRelease               
Hit:4 http://packages.microsoft.com/repos/code stable InRelease                          
Hit:5 http://dl.google.com/linux/chrome/deb stable InRelease                             
Get:6 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]  
Get:7 http://security.ubuntu.com/ubuntu focal-security/main amd64 DEP-11 Metadata [29.0 kB]
Get:8 http://security.ubuntu.com/ubuntu focal-security/universe amd64 DEP-11 Metadata [63.8 kB]
Get:9 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 DEP-11 Metadata [2,468 B]
Fetched 209 kB in 2s (107 kB/s)               
Reading package lists... Done
```

### apt-cache search (...)

This command show package lists that relative to text 'htop'.

```r
mhj@mhj-ideapad:~$ sudo apt-cache search htop
[sudo] password for mhj: 
htop - 대화형 프로세스 뷰어 
aha - ANSI color to HTML converter
libauthen-oath-perl - Perl module for OATH One Time Passwords
pftools - build and search protein and DNA generalized profiles
```
then these packages are that you can download with using _apt_.

### apt-get install (...)

This command will install package, if package exists on _apt-cache_. 

```r
mhj@mhj-ideapad:~$ sudo apt-get install htop
[sudo] password for mhj: 
Reading package lists... Done
Building dependency tree       
Reading state information... Done
htop is already the newest version (2.2.0-2build1).
The following packages were automatically installed and are no longer required:
  linux-headers-5.11.0-27-generic linux-hwe-5.11-headers-5.11.0-27
  linux-image-5.11.0-27-generic linux-modules-5.11.0-27-generic
  linux-modules-extra-5.11.0-27-generic
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
```
'0 upgraded ...' is because htop is already installed in my computer. 

### apt-get upgrade (...)

If you want to upgrade specific software you want, type apt-get upgrade (...). If you just type _apt-get upgrade_, you can upgrade everything that you installed softwares via _apt-get_. 

```r
mhj@mhj-ideapad:~$ sudo apt-get upgrade
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Calculating upgrade... Done
The following packages were automatically installed and are no longer required:
  linux-headers-5.11.0-27-generic linux-hwe-5.11-headers-5.11.0-27
  linux-image-5.11.0-27-generic linux-modules-5.11.0-27-generic
  linux-modules-extra-5.11.0-27-generic
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
```

### apt-get remove (...) 

This command will remove package that you type on (...). Then terminal will ask you whether you really want to remove this package, then just press y. And finally that package is removed from your computer. 

```r
mhj@mhj-ideapad:~$ sudo apt-get remove htop
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  linux-headers-5.11.0-27-generic linux-hwe-5.11-headers-5.11.0-27
  linux-image-5.11.0-27-generic linux-modules-5.11.0-27-generic
  linux-modules-extra-5.11.0-27-generic
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  htop
0 upgraded, 0 newly installed, 1 to remove and 0 not upgraded.
After this operation, 225 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 344468 files and directories currently installed.)
Removing htop (2.2.0-2build1) ...
Processing triggers for mime-support (3.64ubuntu1) ...
Processing triggers for gnome-menus (3.36.0-1ubuntu1) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for desktop-file-utils (0.24-1ubuntu3) ...
```

Then if you execute 'htop', It will fail. 

```r
mhj@mhj-ideapad:~$ htop

Command 'htop' not found, but can be installed with:

sudo snap install htop  # version 3.1.1, or
sudo apt  install htop  # version 2.2.0-2build1

See 'snap info htop' for additional versions.
```

So, If you want to execute 'htop', just do what we learn!


# DIRECTORY STRUCTURE_02

## /home (Home Directories)

This is the user's directory. That is, assuming that there is an mhj as a user of this operating system, there will be a directory called mhj under the home directory.

```
mhj@mhj-IdeaPad:~$ cd /home
mhj@mhj-IdeaPad:/home$ ls
hdd  mhj  newhdd
```
Here, when you want to go to a directory called mhj at once, there is the following method.

```
mhj@mhj-IdeaPad:~$ cd /
mhj@mhj-IdeaPad:/$ pwd
/
mhj@mhj-IdeaPad:/$ cd ~
mhj@mhj-IdeaPad:~$ pwd
/home/mhj
mhj@mhj-IdeaPad:~$
```
Using '~' in this way, it is possible to move to the user's home directory at once.

- Home directories for all users to store their personal files.
- For example: /home/john, /home/nikita

## /boot (Boot Loader Files)

It deals with a very deep part of the Linux operating system. So I'll pass it now.

- Contains boot loader related files.
- Kernel initrd, vmlinux, grub files are located under /boot
- For example: initrd.img-2.6.32-24-generic, vmlinuz-2.6.32-24-generic

## /lib (System Libraries)

It is a place where libraries commonly used by various programs located in bin and sin directories are stored, and this is also a systematic part, so let's move on.

- Contains library files that supports the binaries located under /bin and /sbin
- Library filenames are either ld* or lib*.so.*
- For example: ld-2.11.1.so, libncurses.so.5.7

## /opt (Optional add-on Applications)

When we install software, for example, when we try to install a program called htop using apt-get, it automatically places it in the right place.

```
mhj@mhj-IdeaPad:~$ whereis htop
htop: /usr/bin/htop /usr/share/man/man1/htop.1.gz
```
However, there are times when we have to manually specify a specific directory, and it is also a good idea to install it under the opt.

- opt stands for optional.
- Contains add-on applications from individual vendors.
- add-on applications should be installed under either /opt/ or /opt/ sub-directory.


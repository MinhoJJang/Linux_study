# DIRECTORY STRUCTURE_01

The contents were referred to on the site below.    
[Linux Directory Structure (File System Structure) Explained with Examples](https://www.thegeekstuff.com/2010/09/linux-file-system-structure/)

## / (ROOT)

```r
mhj@mhj-IdeaPad:~$ cd /
mhj@mhj-IdeaPad:/$ pwd
/
mhj@mhj-IdeaPad:/$ ls
bin    dev   lib    libx32      mnt   root  snap      sys  var
boot   etc   lib32  lost+found  opt   run   srv       tmp
cdrom  home  lib64  media       proc  sbin  swapfile  usr
```
_It is the __top-level directory of all directories__. If you delete this directory with the rm-rf command, something very interesting might happen._

- Every single file and directory starts from the root directory.
- Only root user has write privilege under this directory.
- Please note that /root is root user’s home directory, which is not same as /.

## /bin (User Binaries)

```r
mhj@mhj-IdeaPad:/bin$ ls
7z                                   lsmod
7za                                  lsns
7zr                                  lsof
GET                                  lspci
HEAD                                 lspgpot
HTMLLinker                           lsusb
POST                                 ltrace
X                                    luit
etc...
```
_Executable programs are called __binary__ on computers. It is called __bin__ for short. That is, commands used by users are located in the directory __bin__._

- Contains binary executables.
- Common linux commands you need to use in single-user modes are located under this directory.
- Commands used by all the users of the system are located here.
- For example: ps, ls, ping, grep, cp.

## /sbin (System Binaries)

```
mhj@mhj-IdeaPad:/$ cd sbin
mhj@mhj-IdeaPad:/sbin$ ls
ModemManager           getpcaps                     pam_getenv
NetworkManager         getty                        pam_tally
aa-remove-unknown      getweb                       pam_tally2
aa-status              gnome-menus-blacklist        pam_timestamp_check
aa-teardown            groupadd                     paperconfig
accessdb               groupdel                     parted
acpid                  groupmems                    partprobe
add-shell              groupmod                     pccardctl
addgnupghome           grpck                        pivot_root
addgroup               grpconv                      plymouthd
adduser                grpunconv                    popcon-largest-unused
agetty                 grub-bios-setup              popularity-contest
alsa                   grub-install                 poweroff
etc...
```
_There are commands or programs that play this role, such as turning off or rebooting the computer, such as __'reboot', 'shutdown', and 'half'__. __sbin__ has programs used by root users or users who have the purpose of __managing this system__. Ordinary users mainly use commands in the __bin__ directory, and you can think that the programs used by the root user are in the __sbin__._

- Just like /bin, /sbin also contains binary executables.
- But, the linux commands located under this directory are used typically by system aministrator, for system maintenance purpose.
- For example: iptables, reboot, fdisk, ifconfig, swapon

## /etc (Configuration Files)

```r
mhj@mhj-IdeaPad:/$ cd etc
mhj@mhj-IdeaPad:/etc$ ls
GNUstep                        logcheck
NetworkManager                 login.defs
ODBCDataSources                logrotate.conf
PackageKit                     logrotate.d
UPower                         lsb-release
X11                            ltrace.conf
acpi                           machine-id
adduser.conf                   magic
alsa                           magic.mime
alternatives                   mailcap
anacrontab                     mailcap.order
apache2                        manpath.config
apg.conf                       mime.types
apm                            mke2fs.conf
```
Configuration means setting. Setting is when there is a program, when we want to change how it works, we change the setting. And in this Linux, the setting of programs operating in the Unix family is not to have a UI, but to change files.(UI = User Interface means, for example, a method of changing any setting by pressing a button.) The program then refers to the file and refers to how it will work.

For example, the file 'wgetrc' in the etc file is a command we used to download files, and let's go into it. Then, there is the following, which can be changed.
```
mhj@mhj-IdeaPad:/etc$ sudo nano wgetrc

# You can lower (or raise) the default number of retries when
# downloading a file (default is 20).
#tries = 20
```
For reference, it is impossible to modify the file unless it enters sudo authority. Originally, the tries part is annotated, but if '#' is removed, the default value can be changed. From the explanation, it seems to mean that you will try downloading the file 20 times, but if you change it and save it as below, you can change the setting of the command wget. 
```
# You can lower (or raise) the default number of retries when
# downloading a file (default is 20).
tries = 15
```
__etc__ may have settings for programs that have already been installed, settings for the operating system itself, or settings for programs that we have installed. Therefore, when we want to change the settings of the program we installed, it can be estimated that it will be in __etc__.

- Contains configuration files required by all programs.
- This also contains startup and shutdown shell scripts used to start/stop individual programs.
- For example: /etc/resolv.conf, /etc/logrotate.conf

## /var (Variable Files)
```
mhj@mhj-IdeaPad:/var$ ls
backups  crash  local  log   metrics  run   spool
cache    lib    lock   mail  opt      snap  tmp
```
__Variable__ generally means that __capacity or content can be changed__. In other words, most of the contents above have characteristics that can change the content.

The contents of __bin, sbin, and etc__ discussed above __do not change__ until the program is manually updated or the settings are manually changed. However, the var directory is different. For example, let's go into the log directory.
```
mhj@mhj-IdeaPad:/var/log$ ls 
Xorg.0.log          dpkg.log
Xorg.0.log.old      dpkg.log.1
alternatives.log    faillog
alternatives.log.1  fontconfig.log
apport.log          gdm3
apport.log.1        gpu-manager.log
apport.log.2.gz     hp
apport.log.3.gz     installer
apt                 journal
auth.log            kern.log
auth.log.1          kern.log.1
auth.log.2.gz       kern.log.2.gz
```
Files here are stored in the name of a specific file if an error occurs in the process of operating a program. Or, when users access a web server or something, content accumulates here. Therefore, these files have the characteristic that the content is not fixed and can always be changed.

- var stands for variable files.
- Content of the files that are expected to grow can be found under this directory.
- This includes — system log files (/var/log); packages and database files (/var/lib); emails (/var/mail); print queues (/var/spool); lock files (/var/lock); temp files needed across reboots (/var/tmp);

## /tmp (Temporary Files)

```
mhj@mhj-IdeaPad:/tmp$ ls
CoreFxPipe_3e4a6f6c77e9466e9f38b45acbf71dbf
CoreFxPipe_79e642af67a04a24902b1b0c2e327609
CoreFxPipe_vscode.0e6e03b24314023a0bad5df629fc5b99
VSFeedbackVSRTCLogs
clr-debug-pipe-2996-81769-in
clr-debug-pipe-2996-81769-out
config-err-gf1Rkz
dotnet-diagnostic-2996-81769-socket
fcitx-socket-:0
```
__tmp__ is a shortened word for temporary and is a place to store temporary files. Also, when the computer is turned off, all files inside the __tmp__ directory are deleted. Therefore, files that require permanent preservation should not be stored here. However, the best option would be to put files in the tmp directory if it doesn't matter that they are temporarily created or disappeared due to any need because they do not take up the capacity of the computer.

- Directory that contains temporary files created by system and users.
- Files under this directory are deleted when system is rebooted.
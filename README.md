# Tips and tricks
## [Windows](windows-tools.md)
## [bash](bash-tricks.md)
## Linux
### RPM - List the files and directories that are installed with that package.
For example nano package
> `user@linuxacademy:~$ sudo rpm -ql nano`
### Install utility for only downloading RPM package
Downloads nano package in current directory
> `user@linuxacademy:~$ sudo yumdownloader nano`
### Install from RPM package
> `sudo rpm -ivh nano_2.2.6-3_amd64.rpm`

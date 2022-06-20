# Copying a file from Windows to Linux through SSH
If you are working on Windows and need to transfer a file from window to Ubuntu server follow these simple steps

First, Install and configure SSH on your Ubuntu server

Execute the following commands :

$ sudo apt update

$ sudo apt install openssh-server

Enable port 22 SSH in firewall

$ sudo ufw allow 22

Check status whether SSH is running in a linux machine

$ sudo systemctl status ssh

You can start or stop SSH using the following commands

$ sudo systemctl start ssh
$ sudo service ssh stop

## Copy file from Windows to Ubuntu server
Execute this command

scp Filepathinwindows username@ubuntuserverip:linuxserverpath

Example
scp D:/TxtFile.txt root@ipaddress:/home/usr/

Tip: You can also use wildcard pattern to transfer files
Eg: scp D:/Images/* root@ipaddress:/home/usr/Images

Above command will transfer all contents inside image folder to usr/images

On transferring, cmd prompt will ask for password enter your ubuntu password corresponding to user

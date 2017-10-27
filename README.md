# pi-setup
For Raspberry Pi setup workshop

## Write os image on microSD
There are 2 ways to write the os image on microSD.  
One is to use a GUI software like Ether(https://etcher.io/).  
The other way is to use Terminal.

```shell
1. You need to check which disk your mac use for your microSD
$ diskUtil list
/dev/disk0 (internal, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *121.3 GB   disk0
   1:                        EFI EFI                     209.7 MB   disk0s1
   2:          Apple_CoreStorage Untitled                120.5 GB   disk0s2
   3:                 Apple_Boot Recovery HD             650.0 MB   disk0s3

/dev/disk1 (internal, virtual):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:                  Apple_HFS Untitled               +120.1 GB   disk1
                                 Logical Volume on disk0s2
                                 5EF6BAB4-089E-4FBA-9F9D-EF7C5D37AB66
                                 Unencrypted

/dev/disk2 (disk image):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     Apple_partition_scheme                        +182.7 MB   disk2
   1:        Apple_partition_map                         32.3 KB    disk2s1
   2:                  Apple_HFS Google Chrome           182.6 MB   disk2s2

/dev/disk3 (internal, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     FDisk_partition_scheme                        *15.9 GB    disk3
   1:                 DOS_FAT_32 -                       15.9 GB    disk3s1
   
2. Unmount disk
diskutil unmountDisk /dev/<disk name>

For example,
diskutil unmountDisk /dev/disk3

3. Burn image on your microSD(This step takes a few minutes)
sudo dd bs=1 if=<image name> of=/dev/<disk name>

For example,
sudo dd bs=1 if=2016-09-23-raspbian-jessie-lite.img of=/dev/disk3
```

## Update / Upgrage
Open Terminal  
```shell
sudo apt/apt-get update
sudo apt/apt-get upgrade
```

## Change some settings
You can do them with GUI

Go to Menu > Preferences > Raspberry Pi Config
Set Keyboard to US
Set Locale to your Locale
Expand Filesystem
Reboot
Run commands in terminal to update Raspbian for recent bug fixes:
sudo apt-get update OR sudo apt update
sudo apt-get dist-upgrade  OR sudo apt full-upgrade
Enable SSH so you can SSH into the pi from your mac
sudo raspi-config
Interfacing Options > SSH > Enabled
sudo apt install apt-transport-https

For CLI user
```shell
sudo raspi-config

Choose expand filesystem
Reboot

Enable ssh
Reboot
```
![](https://github.com/orz-orz-orz-orz-orz/pi-setup/blob/master/raspi-config.png)

Settings for security
add a new user
```shell
$ sudo adduser ngems-koji
```

## Make your pi secure

add a new user to sudo group
```shell
$ sudo adduser ngems-koji sudo

lock the root
$ sudo passwd -l root

del pi user
$ sudo deluser --remove-home pi

Looking for files to backup/remove ...
Removing user `pi' ...
Warning: group `pi' has no more members.
userdel: user pi is currently used by process 622
/usr/sbin/deluser: `/usr/sbin/userdel pi' returned error code 8. Exiting.
```

Change hostname
```shell
$ sudo raspi-config 
Select Hostname, then change the name from raspberrypi to something
```

install ufw which is a software firewall
```shell
$ sudo apt-get install ufw
```
set up
```shell
$ sudo ufw status
Status: active

basic concept is that deny all packets, then allows some pakets that I need (like ssh)
$ sudo ufw default DENY
$ sudo ufw allow ssh
$ sudo ufw allow 80 (if allows users to access pi via web browsers)

delete rule
$ sudo ufw delete allow 22

set limitation to make pi more secure
$ sudo ufw limit ssh

set log function
$ sudo ufw logging low

enable ufw
$ sudo ufw enable

```

For Raspberry Pi Zero W
https://wp.nyu.edu/koji/2017/10/05/how-to-setup-raspberry-pi-zero-w/

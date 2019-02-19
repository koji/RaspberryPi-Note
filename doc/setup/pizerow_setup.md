# Setup Pi Zero W

## 1.Download OS image
Download Raspbian from the official site   
https://www.raspberrypi.org/downloads/raspbian/


## 2. Format a MicroSD card and Write OS image
The format must be MS-Dos. In terms of Mac, open “Disk Utility” and choose the MicroSD card and Erase the data. By the way, a MicroSD card, 8GB or larger.   
```
$ diskutil list
/dev/disk0 (internal, physical):
#: TYPE NAME SIZE IDENTIFIER
0: GUID_partition_scheme *121.3 GB disk0
1: EFI EFI 209.7 MB disk0s1
2: Apple_CoreStorage Macintosh HD 120.5 GB disk0s2
3: Apple_Boot Recovery HD 650.0 MB disk0s3

/dev/disk1 (internal, virtual):
#: TYPE NAME SIZE IDENTIFIER
0: Apple_HFS Macintosh HD +120.1 GB disk1
Logical Volume on disk0s2
EDB94B94-7478-42A4-AFB6-B932E46BAFC8
Unencrypted

/dev/disk2 (internal, physical):
#: TYPE NAME SIZE IDENTIFIER
0: FDisk_partition_scheme *7.9 GB disk2
1: DOS_FAT_32 BOOT 7.9 GB disk2s1
```

In this case, my disk is disk2.   

```
$ diskutil unmountDisk /dev/disk2
Unmount of all volumes on disk2 was successful
```
Then, move into the folder which has the OS image.  

```
$ sudo dd bs=1m if=2017-09-07-raspbian-stretch-lite.img of=/dev/rdisk2
1768+1 records in
1768+1 records out
1854590976 bytes transferred in 367.071585 secs (5052396 bytes/sec)
```

It takes a few minutes.   

No. 3 and 4 are options for people who don’t want to use a external monitor and a keyboard.   

## 3. Create ssh file on the card
Of course, this need to plugin the SD card.
```
$ touch /Volumes/boot/ssh
```

## 4. Add a few lines to cmdline.txt

Add “modules-load=dwc2,g_ether” between rootwait and quiet.   
More over add “dtoverlay=dwc2” to cmdline.txt .  
```
$ echo "dtoverlay=dwc2" >> /Volumes/boot/config.txt
```

## 5. Turn on Raspberry Pi and connect to the Pi via ssh
Initial settings are followings.
```
User name: pi
Host name: raspberrypi
Password: raspberry
```

## 6. Update OS
```
$ sudo apt-get update
$ sudo apt-get upgrade
```

## 7. Add a new user and delete pi user(for security)
https://gist.github.com/koji/0b8e99c7995039b278f3718974a09740

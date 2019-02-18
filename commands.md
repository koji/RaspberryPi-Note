# 22 Basic Commands

```
$ sudo apt-get update # Update Package Lists

$ sudo apt-get upgrade # Download and Install Updated Packages

$ sudo apt-get clean # Clean Old Package Files

$ sudo raspi-config # Pi Configuration Tool

$ ls # List Directory Contents

$ cd # Change Directories

$ mkdir/md # Create a Dir

$ rmdir/rm -rf # remove a Dir

$ mv # Move a file

$ tree -d # show a tree of Dir

$ pwd # Show the Current Dir

$ clear # Clearing the Terminal Window

$ sudo power-off/sudo halt # Shoud down pi

$ sudo reboot # Reboot pi

$ startx # start Desktop

$ ifconfig # Show pi's IP/MAC address etc

$ vim/nano # editor

$ cat # Shows The Contents of a File

$ rm # remove file * Do not type rm *

$ cp # copy a file or Dir

$ history # Show commands' history

$ pinout # Check GPIO

,--------------------------------.
| oooooooooooooooooooo J8     +====
| 1ooooooooooooooooooo        | USB
|                             +====
|      Pi Model ???V1.3          |
|      +----+                 +====
| |D|  |SoC |                 | USB
| |S|  |    |                 +====
| |I|  +----+                    |
|                   |C|     +======
|                   |S|     |   Net
| pwr        |HDMI| |I||A|  +======
`-| |--------|    |----|V|-------'

Revision           : a020d3
SoC                : BCM2837
RAM                : 1024Mb
Storage            : MicroSD
USB ports          : 4 (excluding power)
Ethernet ports     : 1
Wi-fi              : False
Bluetooth          : False
Camera ports (CSI) : 1
Display ports (DSI): 1

J8:
   3V3  (1) (2)  5V
 GPIO2  (3) (4)  5V
 GPIO3  (5) (6)  GND
 GPIO4  (7) (8)  GPIO14
   GND  (9) (10) GPIO15
GPIO17 (11) (12) GPIO18
GPIO27 (13) (14) GND
GPIO22 (15) (16) GPIO23
   3V3 (17) (18) GPIO24
GPIO10 (19) (20) GND
 GPIO9 (21) (22) GPIO25
GPIO11 (23) (24) GPIO8
   GND (25) (26) GPIO7
 GPIO0 (27) (28) GPIO1
 GPIO5 (29) (30) GND
 GPIO6 (31) (32) GPIO12
GPIO13 (33) (34) GND
GPIO19 (35) (36) GPIO16
GPIO26 (37) (38) GPIO20
   GND (39) (40) GPIO21

For further information, please refer to https://pinout.xyz/

```

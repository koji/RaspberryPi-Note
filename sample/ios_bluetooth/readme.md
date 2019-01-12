# Bluetooth settings
```zsh
# check current status

$ hciconfig -a
hci0:	Type: Primary  Bus: UART
	BD Address: B8:27:EB:xx:xx:xx  ACL MTU: 1021:8  SCO MTU: 64:1
	UP RUNNING
	RX bytes:799 acl:0 sco:0 events:52 errors:0
	TX bytes:2520 acl:0 sco:0 commands:52 errors:0
	Features: 0xbf 0xfe 0xcf 0xfe 0xdb 0xff 0x7b 0x87
	Packet type: DM1 DM3 DM5 DH1 DH3 DH5 HV1 HV2 HV3
	Link policy: RSWITCH SNIFF
	Link mode: SLAVE ACCEPT
	Name: 'raspberrypi'
	Class: 0x480000
	Service Classes: Capturing, Telephony
	Device Class: Miscellaneous,
	HCI Version: 4.2 (0x8)  Revision: 0xfc
	LMP Version: 4.2 (0x8)  Subversion: 0x6119
	Manufacturer: Broadcom Corporation (15)
  
# change the name
sudo hciconfig hci0 name rspi3

$ hciconfig -a
hci0:	Type: Primary  Bus: UART
	BD Address: B8:27:EB:A6:5A:54  ACL MTU: 1021:8  SCO MTU: 64:1
	UP RUNNING
	RX bytes:1086 acl:0 sco:0 events:56 errors:0
	TX bytes:2784 acl:0 sco:0 commands:56 errors:0
	Features: 0xbf 0xfe 0xcf 0xfe 0xdb 0xff 0x7b 0x87
	Packet type: DM1 DM3 DM5 DH1 DH3 DH5 HV1 HV2 HV3
	Link policy: RSWITCH SNIFF
	Link mode: SLAVE ACCEPT
	Name: 'rspi3'
	Class: 0x480000
	Service Classes: Capturing, Telephony
	Device Class: Miscellaneous,
	HCI Version: 4.2 (0x8)  Revision: 0xfc
	LMP Version: 4.2 (0x8)  Subversion: 0x6119
	Manufacturer: Broadcom Corporation (15)


```


# Bluetooth(Peripheral) 

In this case, iOS=Central and pi=Peripheral

## Install libs
```zsh
$ sudo apt-get update
$ sudo apt-get install bluetooth bluez libbluetooth-dev libudev-dev
$ sudo apt-get install libdbus-1-dev libdbus-glib-1-dev libglib2.0-dev libical-dev
```

## Install nodejs via n
There are a couple of options to install nodejs. apt-get/nodebrew/nvm/source code. This sample uses `n` (https://github.com/tj/n)
```zsh
$ sudo apt-get install curl
$ curl -L https://git.io/n-install | bash
# need to set PATH
$ ~/.bashrc or ~/.zshrc
$ n 9.11.2
```

## Install bleno
```zsh
$ npm -v
5.6.0
$ mkdir iosandpibluetooth
$ cd iosandpibluetooth/
$ npm init -y
$ npm install bleno --save
```

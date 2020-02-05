# Format USB

`Guide to format usb after using it as live media or if partion is messed up.`

**Writer**: Abhay Shanker Pathak

**Source**: Various

## Delete partition:

Follow these steps to delete the partion of pendrive:
```sh
	$ sudo fdisk /dev/sdX	#X is your partion name
	# use m for help in fdisk
	Command (m for help): d	#this will delete the partion
	# if necessary select number of partion
	Command (m for help): w	#this will write in usb
```

## Create Partition:

```sh
	$ lsblk	#tells all about the partitions, note the usb name from it
	$ sudo fdisk /dev/sdX
	Command (m for help): n	#this will create new parition
	Partition type
	p (primary)
	e (extended)
	Select (default p): p	# this will create primary parition
	Partition number (1-4, default 1):1
	Fisrt Sector(......): # press return
	Last Sector(......): # press return
	Command (m for help): w
	$ sudo partprobe -d
	$ sudo partprobe -s
	/dev...
	/dev....
	....
```

## Format:

```sh
	$ sudo mkfs.vfat -F 32 /dev/sdX1	# use name of partition you want to format
	$ lsblk
	$ mkdir ~/cell
	$ sudo mount /dev/sdX1 ~/cell	# this will mount the usb, means you can now access usb from this folder.
	# to remove usb, type
	$ sudo umount ~/cell	#**OR**
	$ sudo umount /dev/sdX1	# now remove the pendrive
```

# check the attached disk
- lsblk
The fdisk command in Linux is a powerful command-line utility used for managing disk partitions. It allows users to create, delete, resize, and manage partitions on hard drives or other storage devices. While primarily used for managing Master Boot Record (MBR) partition tables, fdisk also supports other partition table types like GPT, Sun, SGI, and BSD. 
for all drives partitions
```
sudo fdisk -l
```
for specific command accordingly
```
sudo fdisk -l /dev/sdX
```
X name of the drive

# Key functionalities of fdisk:
## Listing partitions:
The fdisk -l command can be used to view information about all disk partitions on your system, or on a specific device by adding the device path (e.g., fdisk -l /dev/sda).
Creating partitions:
When run with a device path (e.g., fdisk /dev/sda), fdisk enters an interactive mode where you can use commands like n (new) to create new primary or extended partitions.
Deleting partitions:
In interactive mode, the d command is used to delete existing partitions.
Changing partition type:
The t command allows you to change the type of a partition, with l providing a list of supported partition types and their hex codes.
Saving and exiting:
The w command writes the changes made to the partition table to the disk, while q exits fdisk without saving any changes.
Viewing commands:
Typing m in interactive mode displays a list of available commands within fdisk.


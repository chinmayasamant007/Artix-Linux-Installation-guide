#                                                  Artix-Linux-Installation-guide
 *Format the disks*
partition you hard drive (/dev/sda will be used in this guide) with `fdisk`or `fdisk`

```
 cfdisk /dev/sda1 => EFI partition => 550 => mkfs.fat -F32 /dev/sda1

 cfdisk /dev/sda2 => EXT4 partition => 30G => mkfs.ext4 /dev/sda2 
 
 cfdisk /dev/sda3 => Should Already be there
 
 ```
*Mount the drives*
```
 - dev/sda1 =>  /mnt/boot/EFI
 
 - /dev/sda2 => /mnt
 
 - /dev/sda3 => /mnt/home

 ```
``` basestrap /mnt base basel=-devel runit elogind-runit linux-lts linux-lts-headers linux-firmware
fstabgen -U /mnt > /mnt/etc/fstab
```

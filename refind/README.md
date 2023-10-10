## refind bootloader
just copy refind directory to any FAT16/32 partition and you are good to go. btrfs,ext4 drivers are all ready installed.
```
some partition root/EFI/refind/+
 - refind/
 - refind.conf
```
It can detect os through partition labels, and show coresponding logo.


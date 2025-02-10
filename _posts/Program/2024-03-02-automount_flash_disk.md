---
layout: post
title: Автомонтирование дисков
category: Program
---

### В моем случае(узнать и смонтировать):

- bash-5.1$ lsblk

        NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS

        sda      8:0    0 447,1G  0 disk

        ├─sda1   8:1    0   500M  0 part /boot/efi

        └─sda2   8:2    0 446,6G  0 part /

        sdb      8:16   1     0B  0 disk

        sdc      8:32   1  57,8G  0 disk

        └─sdc1   8:33   1  57,8G  0 part

- mount -t auto /dev/sdc1 /home/jenit/usb

### Размонтировать:

- bash-5.1# umount /dev/sdc1



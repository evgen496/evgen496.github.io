---
layout: post
title: Подключение раздела с NTFS
category: Fluxbox
---

#### Подключите раздел NTFS с разрешениями на чтение и запись.

Чтобы смонтировать раздел NTFS с разрешениями на чтение и запись, убедитесь что  установлены Fuse и ntfs-3 в вашей системе.

Для завершения процесса монтажа выполните следующие действия:

#### Монтировать раздел NTFS

Сначала создайте точку монтирования с помощью **mkdir** команды:

- sudo mkdir /mnt/ntfs2

Затем используйте команду монтирования к **mount** нужному разделу.

**Например, /dev/sdb2:**

- sudo mount -t ntfs-3g /dev/sdb2 /mnt/ntfs2/

Чтобы проверить, смонтирован ли раздел, выполните **df** команду:

- df -hT

#### Universal

- lsblk - узнать букву подключаемого раздела

- mount -t auto /dev/sd* /home/jenit/usb - подключить раздел

- umount /dev/sd* - отключить раздел

---
layout: post
title: Обновления ядра elilo
category: Slackware
---

Недавно я поставил slackware, c использованием uefi и elilo и после обновления ядра получил ошибку невозможности загрузить ядро.

С lilo последнее время достаточно после обновления ядра выполнить команду:

- lilo

Но с elilo так не получится.

И команда eliloconfig тоже не исправляет ситуацию, даже после обновления initrd.

Вся проблема происходит из-за того, что новый initrd не копируется в папку /boot/efi/EFI/Slackware/.

По этому после обновления ядра в Slackware новое ядро и initrd необходимо скопировать руками, выполнить, например такие команды:

- cp -v /boot/initrd.gz /boot/efi/EFI/Slackware/

- cp -v /boot/vmlinuz-generic-5.16.15 /boot/efi/EFI/Slackware/

- cp -v /boot/vmlinuz-huge-5.16.15 /boot/efi/EFI/Slackware/

Ядро huge вроде как не обязательно было копировать, но для надежности я перенес все.

#### Подводя итоги:

После обновления ядра в slacware нужно пересобрать initrd и скопировать его и новое ядров в папку с EFI.

1:

- mkinitrd -c -k 5.13.4 -r /dev/sda1 -f ext4 -m ext4

2:

- cp -v /boot/initrd.gz /boot/efi/EFI/Slackware/

- cp -v /boot/vmlinuz-generic-5.16.15 /boot/efi/EFI/Slackware/


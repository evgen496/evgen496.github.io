---
layout: post
title: Обновление ядра в Slackware
category: Slackware
---

### Обновление ядра в Slackware 15

(Обновлял ядра в версиях 14.2 и 15)

1) /usr/share/mkinitrd/mkinitrd_command_generator.sh -k 5.15.145 \| bash

2) mkinitrd -c -k 5.15.145 -m ext4 -r /dev/sda2 -f ext4

Но они не очень удобны тем, что нужно предварительно посмотреть на версию свежеустановленного ядра, чтобы указать ее в параметрах и не опечататься, равно как и в других параметрах.

Второй способ проверен несколько раз.Работает.

Первый не пробовал.Думаю тоже рабочий.


### Делаю так:

- slackpkg update

- slackpkg update gpg

- slackpkg upgrade-all

### С lilo:

- lilo

-  mkinitrd -c -k 5.15.145 -m ext4 -r /dev/sda2 -f ext4 (смотрите версию своего ядра - мое ядро 5.15.145 и номер корневого раздела.У меня это /dev/sda2)

- lilo

### С elilo:

Генерируем новый initrd:

mkinitrd -c -k 5.15.145 -r /dev/sda2 -f ext4 -m ext4

Обновляем загрузчик (в моем случае это elilo):

- eliloconfig && lilo

Переносим вручную новый initrd и vmlinuz в каталог загрузки:

- cp -v /boot/initrd.gz /boot/efi/EFI/Slackware/

- cp -v /boot/vmlinuz-generic-5.15.38 /boot/efi/EFI/Slackware/

Проверяем конфиг (на всякий случай):

- vim /boot/efi/EFI/Slackware/elilo.conf

Перед ребутом можно выполнить чтобы проверить версию ядра до/после ребута:

- uname -r

Ребутимся и проверяем версию ядра


P.S.

в /etc/slackpkg/blacklist - ***ничего не надо изменять что касается ядра***




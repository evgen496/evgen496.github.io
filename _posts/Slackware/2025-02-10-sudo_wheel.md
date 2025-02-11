---
layout: post
title:  Добавить пользователя в группу wheel
category: Slackware
---

Чтобы добавить пользователя в группу wheel в системе, используется команда:

- su

- pass: ******

__usermod -aG wheel *username*__

- reboot

Вместо *username* нужно указать имя пользователя, которого нужно добавить.

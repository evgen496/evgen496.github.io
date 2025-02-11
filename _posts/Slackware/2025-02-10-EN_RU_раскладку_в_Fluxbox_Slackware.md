---
layout: post
title:  Переключить EN_RU раскладку во Fluxbox
category: Slackware
---

Поместить в 

- nano ~./fluxbox/startup

**setxkbmap -layout "us,ru" -option "grp:caps_toggle,grp_led:scroll"**

Это моя расскладка. Вы можете сделать по своему.

Установить локаль на определенное приложение 

- nano /etc/sudoers

**export LC_ALL=ru_RU.UTF-8**

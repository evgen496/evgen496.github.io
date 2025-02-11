---
layout: post
title: Fluxbox Slackware 15 (wallpaper)
category: Slackware
---

Начиная с версии 0.9.* во Fluxbox появился скрипт fbsetbg, использующий для установки фона рабочего стола такие программы, как chbg, wmsetbg, display, qiv, xsetbg. 

Для того, чтобы после очередной загрузки выставлялся выбранный фон рабочего стола в файл ~/fluxbox/init при настройке Fluxbox следует добавить строку:

session.screen0.rootCommand: fbsetbg -l. 

В каталоге ~/.fluxbox я создаю подкаталог backgrounds, куда и складываю подборку обоев.

Затем там же создаю файл lastwallpaper следующего содержания:

- ~$ nano .fluxbox/lastwallpaper

- $ full|/home/jenit/.fluxbox/backgrounds/future-1920x1200.jpg|:0.0

Больше не требуется feh, nitrogen.

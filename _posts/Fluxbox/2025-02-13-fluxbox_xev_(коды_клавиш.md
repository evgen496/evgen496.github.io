---
layout: post
title:  Fluxbox - узнать код клавиши
category: Fluxbox
---

Узнать это просто, стандартными средствами иксов - программой **xev**.

Запускаем терминал,пишем в ней xev (от пользователя).

Появится белое окошко, которое будет регистрировать всё, что происходит с мышью.

Пробуем нажимать клавиши и смотрим, что получается.

Например, жмём на кнопку **Space**(пробел), должны увидеть что то типа этого:
```
KeyRelease event, serial 33, synthetic NO, window 0xe00001, root 0x4c, subw 0x0, time 8095640, (-57,293), root:(753,322), state 0x0, keycode 65 (keysym 0x20, space), same_screen YES, XLookupString gives 0 bytes
```
То, что написано после **keycode**, и есть код клавиши и в скобках название клавиши.

Пробуем клавишу - если видим какой-нибудь keycode, значит работает.



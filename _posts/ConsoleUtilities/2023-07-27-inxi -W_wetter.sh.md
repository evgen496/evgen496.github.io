---
layout: post
title:  water.sh, inxi -W Kamchatka,Russia
category: ConsoleUtilities
---

#wetter #konsole

#### water.sh

Сам скрипт:
```
#!/bin/sh
 curl -4 wttr.in/Petropavlovsk-Kamchatsky
```
#### Сделать исполняемым:

- chmod +x water.sh

#### Предотвратить закрытие окна терминала после выполнения скрипта sh кнопкой запуска:

konsole --hold -e "/home/jenit/bin/water.sh"

or

konsole -hold -e "/home/jenit/bin/water.sh" (in MATE)

(директорию /bin прописать в .bashrc - export PATH=$PATH:/home/user/bin)

(.bashrc - скрытый файл в домашнем каталоге. Ctrl + H - показать/скрыть скрытые файлы и каталоги)

![](/img/files/water_rosa_hotkey.png)

#### Сам скрипт:

 #!/bin/bash

 curl -4 wttr.in/Petropavlovsk-Kamchatsky

#### Еще погода!

 P.S.еще можно с помощью программы inxi:
 
inxi -W Kamchatka,Russia(вместо Камчатки ваш город или регион)

Установить:

 inxi - sudo dnf install inxi

 ![water](/img/inxi-W.png)

 Так же командой:

 - $ inxi -w

 ![](/img/water_inxi.png)

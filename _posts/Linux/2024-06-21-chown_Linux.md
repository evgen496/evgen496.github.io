---
layout: post
title:  Команда chown Linux
category: Linux
---

### Синтаксис и опции

Синтаксис chown, как и других подобных команд linux очень прост:

- $ chown пользователь опции /путь/к/файлу

В поле пользователь надо указать пользователя, которому мы хотим передать файл.

Также можно указать через двоеточие группу, например, пользователь:группа.

Тогда изменится не только пользователь, но и группа.

Вот основные опции, которые могут вам понадобиться:

- -c, --changes - подробный вывод всех выполняемых изменений

- -f, --silent, --quiet - минимум информации, скрыть сообщения об ошибках

- --dereference - изменять права для файла к которому ведет символическая ссылка вместо самой ссылки (поведение по умолчанию)

- -h, --no-dereference - изменять права символических ссылок и не трогать файлы, к которым они ведут

- --from - изменять пользователя только для тех файлов, владельцем которых является указанный пользователь и группа

- -R, --recursive - рекурсивная обработка всех подкаталогов

- -H - если передана символическая ссылка на директорию - перейти по ней

- -L - переходить по всем символическим ссылкам на директории

- -P - не переходить по символическим ссылкам на директории (по умолчанию)


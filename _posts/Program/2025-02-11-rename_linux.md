---
layout: post
title:  Команда rename
category: Program
---

#rename

### Замена расширения .txt на .md всех файлов в директории Линукс.

<mark>Простая команда, rename от util-linux, сделает это за вас. Он заменяет все вхождения "txt" на "md" во всех файлах, соответствующих "*.txt":</mark>

- <mark>rename txt md *.txt</mark>

### В Ubuntu 18.04 команда util-linux rename доступна как rename.ul.

Это сработало для меня:

- rename.ul -o -v .oldext .newext *.oldext

Параметры:

    -o: не перезаписывать уже существующий .newext
    -v: многословный
    -n: пробный прогон

Для получения дополнительной информации см. man rename.ul или rename.ul -h.

### Переименование командой rename

Команда rename служит для массового (пакетного) переименования файлов. Она позволяет выполнять замену определенных символов или частей имени файла и использованием Perl-регулярных выражений.

Если вдруг в вашем дистрибутиве нет команды rename, то ее можно установить, выполнив (выберите соответствующую команду для вашего дистрибутива):

- pkg install rename

- sudo apt install rename

- sudo yum install prename

- yaourt -S perl-rename

### Синтаксис команды rename:

rename опции ’s/старое_имя/новое_имя’ файлы

старое_имя — регулярное выражение или часть имени файла, которое нужно заменить на новое_имя.

новое_имя — задает результирующее имя файла (может быть регулярным выражением).

### Основные опции:

- -f — перезаписывать существующие файлы.

- -n — вывести список файлов, которые будут переименованы и их новые имена, но не выполнять переименование.

- -v — вывести список обработанных файлов.

**Проще всего понять, как пользоваться данной командой, на примерах**.

### Изменение расширения файлов

#### Массово изменить расширение .html на .php у всех html-файлов.

- rename 's/.html/.php/' *.html

По умолчанию rename ***не перезаписывает существующие файлы***. Чтобы существующие файлы ***перезаписывались***, используется опция -f:

- rename -f 's/.html/.php/' *.html

#### Замена пробелов на подчеркивание

Заменить все символы пробелов в имени файлов на символ подчеркивания:

- rename 'y/ /_/' *

Конвертация имен файлов в строчные буквы

- rename 'y/A-Z/a-z/' *

Конвертация имен файлов в прописные буквы

- rename 'y/a-z/A-Z/' *

#### Показать, что именно будет переименовано, но не переименовывать

Чтобы избежать ошибок при переименовании файлов, особенно при использовании сложных регулярных выражений, можно сначала вывести список того, что будет переименовано, но не запускать само переименование. Для этого служит опция -n.

#### Например, мы хотим изменить расширение у файлов с .jpeg на .jpg.

Используем опцию -n, чтобы просто вывести какие файлы будут переименованы:

- rename -n 's/\.jpeg$/.jpg/' *

Полное описание команд mv и rename можно получить, выполнив в терминале команду:

- man rename

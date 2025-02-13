Static-get — инструмент, с помощью которого можно скачать статически слинкованный бинарный файл нужной нам утилиты. Такой файл будет работать практически на любом дистрибутиве. В данный момент, в базе static-get доступно 930 пакетов и количество постепенно растёт.

Установка и использование.
Каких-то специфических шагов для установки делать не потребуется, но наличие wget (почему-то без него первый запуск скрипта не выполнялся корректно) и tar будет обязательным.


# dnf install git wget tar


Исполняемый файл static-get — это по сути скрипт, так что достаточно будет просто клонировать репозиторий с ним, и он уже будет готов к использованию.


# git clone https://github.com/minos-org/minos-static
# cd minos-static/
# ./static-get


Итак, с помощью скрипта мы можем: выполнить поиск нужной программы, скачать архив с ней, обновить её при необходимости, установить программу в систему и удалить её.

Скрипту так же можно передать некоторые параметры для работы — в каком репозитории искать пакеты, для какой архитектуры, какого формата они должны быть. Имеется возможность выполнить dry-run запуск или выполнить установку в verbose режиме. Несколько примеров работы ниже:

— Скачиваем и запускаем nano:


# ./static-get --extract nano
# ./nano/bin/nano --version
GNU nano, version 2.4.2
(C) 1999..2015 Free Software Foundation, Inc.
Email: nano@nano-editor.org Web: http://www.nano-editor.org/
Compiled options: --disable-libmagic --disable-nls --disable-utf8



— Устанавливаем qemu в систему:


# ./static-get --install qemu
qemu-1.4.0-1.tar.xz
# /bin/qemu-io --version
qemu-io version 0.0.1


— Удаляем qemu:


# ./static-get --remove qemu
# /bin/qemu-io --version
-bash: /bin/qemu-io: No such file or directory


— Ищем gcc в репозитории:


# ./static-get --search gcc
gcc-4.6.1-2.tar.xz:672ba63bc0dd505104f22e4c3295c0e6


В своей работе static-get базируется на нескольких проектах — bifrost-autobuild, morpheus-autobuild, rlsd2-autobuild, misc-autosync. Бинарные файлы описываются в специальных рецетах (предпочтительны рецепты для bifrost), а после сборки архивы с пакетами публикуются в репозитории s.minos.io, откуда скриптом и выполняется установка.

@linuxchmod

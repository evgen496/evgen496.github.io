---
layout: post
title: Slackware
category: Slackware
---

#### Добавить нового пользователя:

`adduser`

В диалоговом окне, которое появляется, когда это появляется:

`Additional UNIX groups:`

нажмите клавишу вверх на клавиатуре и в конце строки группы, которая автозаполняется с указанной клавишей, добавьте: **колесо** и нажмите **вводить**.

#### Включите sudo для нашего пользователя:

`nano /etc/sudoers`

Раскомментировать (#):

`%wheel ALL=(ALL) ALL`

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

#### Переведите систему на испанский язык:

Перечислите все доступные языки: **locale -a**

`nano /etc/profile.d/lang.sh`

Заменить экспорт LANG = en_US:

`export LANG=es_ES.utf8`

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

`nano /etc/profile.d/lang.csh`

Заменить setenv LANG en_US:

`setenv LANG es_ES.utf8`

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

#### Настроить репозитории:

`nano /etc/slackpkg/mirrors`

Раскомментируйте Российский репозитории или на Ваш выбор.

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

#### Система обновлений:

обновление slackpkg обновление slackpkg gpg обновление slackpkg-все

#### Запустите систему в графическом режиме (DM):

`nano /etc/inittab`

Изменить id: 3: initdefault: на:

`id:4:initdefault:`

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

#### Измените время ожидания lilo с двух минут на пять секунд:

`nano /etc/lilo.conf`

Замените timeout = 2000 на:

`timeout=50`

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

`/sbin/lilo`

Теперь мы устанавливаем очень полезный инструмент, который скомпилирует и установит за нас программы:

wget http://sbopkg.googlecode.com/files/sbopkg-0.37.0-noarch-1_cng.tgz installpkg sbopkg-0.37.0-noarch-1_cng.tgz

Обновляем базу программ, доступных на Slackbuilds.org:

`sbopkg -r`

#### Как установить пакеты через sbopkg…?

Мы проверяем, что пакет доступен по адресу http://slackbuilds.org/, и отмечаем все зависимости.  
Тогда просто запустите: **sbopkg -i "тонкий"** (Это пример установки слима). Не забывайте, что перед тем, как поставить пакет, который мы хотим установить, мы помещаем все его зависимости. Теперь устанавливаем основные программы:

#### Если мы используем ноутбук:

`sbopkg -i "kcm_touchpad"`

#### VLC:

sbopkg -i "orc texi2html libebml libmp4v2 libcuefile libreplaygain lame x264 a52dec faad2 speex twolame lua lua portaudio libass libavc1394 libdc1394 libdca libdvbpsi libdvdcss libdvdningerdibdvbpsi libsupport libdvdnavlibgd2dinagerdlibmatroska tools fautplagerdlibmatroska инструментарий libmpeplagerdlibmatroska инструментарий libmpexlibmpexlab

#### Инструменты сжатия:

`sbopkg -i "p7zip rar unrar libtar"`

#### Ява:

В случае использования 32-битной системы:

Загрузите jdk от oracle в его версии 7u51 (jdk-7u51-linux-i586.tar.gz):

http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html#jdk-7u51-oth-JPRDescargar slackbuild:

Скачиваем slackbuild:  
`wget http://slackbuilds.org/slackbuilds/14.1/development/jdk.tar.gz`

Разархивируйте jdk.tar.gz

Вставьте файл jdk-7u51-linux-i586.tar.gz в папку jdk, которую мы распаковали ранее, и запустите сценарий:

`./jdk.SlackBuild`

Это создаст такой устанавливаемый пакет (вы всегда видите путь и имя сгенерированного пакета), и мы устанавливаем его с помощью:

`installpkg /tmp/jdk-7u51-i586-1_SBo.tgz`

#### В случае использования 64-битной системы:

Загрузите jdk от oracle в его версии 7u51 (jdk-7u51-linux-x64.tar.gz):  
http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html#jdk-7u51-oth-JPR

Скачиваем slackbuild:  
`wget http://slackbuilds.org/slackbuilds/14.1/development/jdk.tar.gz`

Разархивируйте jdk.tar.gz

Вставьте файл jdk-7u51-linux-x64.tar.gz в папку jdk, которую мы распаковали ранее, и запустите скрипт:

`ARCH=x86_64 ./jdk.SlackBuild`

Это создаст такой устанавливаемый пакет (вы всегда видите путь и имя сгенерированного пакета), и мы устанавливаем его с помощью:

`installpkg /tmp/jdk-7u51-x86_64-1_SBo.tgz`

#### Flash:

`sbopkg -i "flashplayer-plugin"`

#### Либреофис:

`sbopkg -i "libreoffice"`

#### Перевести Libreoffice:

Загрузите slackbuild-файлы libreoffice-helppack и libreoffice-langpack:

wget http://slackbuilds.org/slackbuilds/14.1/office/libreoffice-helppack.tar.gz wget http://slackbuilds.org/slackbuilds/14.1/office/libreoffice-langpack.tar.gz

Распаковываем скачанные файлы.

Скачиваем пакеты libreoffice:

#### 32 бит:

wget http://download.documentfoundation.org/libreoffice/stable/4.2.3/rpm/x86/LibreOffice_4.2.3_Linux_x86_rpm_helppack_es.tar.gz
wget http://download.documentfoundation.org/libreoffice/stable/4.2.3/rpm/x86/LibreOffice_4.2.3_Linux_x86_rpm_langpack_es.tar.gz

Мы вставляем эти файлы, не распаковывая их, в соответствующие папки slackbuid и выполняем скрипт в обоих:

./libreoffice-helppack.SlackBuild ./libreoffice-langpack.SlackBuild

И устанавливаем сгенерированные пакеты (вы всегда видите путь и имя сгенерированного пакета):

installpkg /tmp/libreoffice-helppack-4.2.3_es-i586-1_SBo.tgz
installpkg /tmp/libreoffice-langpack-4.2.3_es-i586-1_SBo.tgz

#### 64 бит:

wget http://download.documentfoundation.org/libreoffice/stable/4.2.3/rpm/x86_64/LibreOffice_4.2.3_Linux_x86-64_rpm_helppack_es.tar.gz
wget http://download.documentfoundation.org/libreoffice/stable/4.2.3/rpm/x86_64/LibreOffice_4.2.3_Linux_x86-64_rpm_langpack_es.tar.gz

Мы вставляем эти файлы, не распаковывая их, в соответствующие папки slackbuid и выполняем скрипт в обоих:

ARCH = x86_64 ./libreoffice-helppack.SlackBuild ARCH = x86_64 ./libreoffice-langpack.SlackBuild

И устанавливаем сгенерированные пакеты (вы всегда видите путь и имя сгенерированного пакета):

installpkg /tmp/libreoffice-helppack-4.2.3_es-x86-64-1_SBo.tgz
installpkg /tmp/libreoffice-langpack-4.2.3_es-x86-64-1_SBo.tgz

#### Filezilla**:**

`sbopkg -i "wxPython filezilla"`

#### Skype:

`sbopkg -i "skype"`

#### TeamViewer:

`wget http://download.teamviewer.com/download/teamviewer_linux.tar.gz`

Разархивируйте его, и, не устанавливая, мы можем использовать его, выполнив пакет teamviewer в этой папке.

#### Брандмауэр:

`sbopkg -i "ufw"`

Добавляем пакет в стартовый список:

`nano /etc/rc.d/rc.local`

Пишем это в конце:

если [-x /etc/init.d/ufw]; затем /etc/init.d/ufw start fi

Сохраняем документ с помощью CTRL + O и закрываем с помощью CTRL + X.

Включаем фаервол:

`ufw enable`

Мы разрешаем ssh, если мы его используем:

`ufw allow ssh`

#### Новое меню запуска для KDE, если вам интересно (как на изображении):

`sbopkg -i "homerun"`

И вуаля .. Таким образом они получают систему, подготовленную для общего использования: D. И вы видите, что это не так сложно, как может показаться. Приветствую linuxeros и не забываем комментировать :).

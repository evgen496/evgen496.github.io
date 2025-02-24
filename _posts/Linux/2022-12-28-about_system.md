---
layout: post
title: Просмотр данных о системе(касается Linux)
category: Linux
---

### Эти утилиты из "коробки"

***Какая "операционка"(система) установлена*** (*как узнать*)

- cat /etc/os-pelease
- cat /etc/*-release
- cat /proc/version
- lsb_release -a

***Более расширенные данные***

- uname -a

***Посмотреть справку об uname***

- uname --help

***Сама справка (help)***:

Использование: **uname [ПАРАМЕТР]**…

Печатает определенные сведения о системе.

**Если ПАРАМЕТР не задан, то
подразумевается -s**.

 -  -a, --all              напечатать всю информацию, в следующем порядке,
                         кроме -p и -i, если они неизвестны:

 -  -s, --kernel-name      напечатать имя ядра

-   -n, --nodename         напечатать имя машины в сети

-   -r, --kernel-release   напечатать информацию о выпуске ядра

-   -v, --kernel-version     напечатать версию ядра

-   -m, --machine            напечатать тип оборудования машины

-  -p, --processor          напечатать тип процессора (непереносима)

  - -i, --hardware-platform  напечатать тип аппаратной платформы (непереносима)

 -  -o, --operating-system   напечатать имя операционной системы
      --help     показать эту справку и выйти
      --version  показать информацию о версии и выйти


>Страница справки по GNU coreutils: https://www.gnu.org/software/coreutils/
>
>Об ошибках в переводе сообщений сообщайте по адресу https://translationproject.org/team/ru.html
>
>Полная документация: https://www.gnu.org/software/coreutils/uname
>
>или доступная локально: info '(coreutils) uname invocation'

***Программа "inxi".В Slackware 15 установлена по умолчанию***.

В других дистрибутивах возможно придется,если есть необходимость,установить.

**Использование** (как делаю я)

- inxi -IPS

***Краткая расшифровка***:

>- **-I, --info** 
>
>Общая информация, включая процессы, время безотказной работы, память,
	          тип IRC-клиента или оболочки, в версии OC. 

>- **-P, --partitions**
>
>Основная информация о разделах.
>
>Воспользуйся **-p** чтобы просмотреть все смонтированные разделы.


>- **-S, --system**  
>
>Информация о системе: host name, kernel (ядро), desktop environment (среда рабочего стола) 
               (if in X/Wayland), distro (дистрибутив). 


***Все данные об утилите также с помощью***:

- inxi --help

#### **Сведения о компьютере**

- sudo lshw

- sudo lshw -short

*Немного дополним предыдущую команду*:

- sudo lshw -html > system_info.html

И в домашней директории появился файл **system_info.html**, который мы сможем просмотреть в любом интернет браузере.

## Информация об оперативной памяти в Linux. Свободная, занятая и тип памяти

#### **Команда free**

Команда **free** очень простая, она выводит информацию о общем количестве оперативной памяти, о количестве занятой и свободной памяти, а также об использовании файла подкачки.

По умолчанию объем памяти выводится в килобайтах. Используя опции, можно выводить объем памяти в других форматах. 

Некоторые опции:

- -m — в мегабайтах

- -g — в гигабайтах

- -h — автоматически определить формат

Пример:

- $ free

- $ free -m

#### **Команда vmstat**

Команда **vmstat** выводит различную статистику по использованию памяти. 

Используя ключ **-s** можно вывести подробную статистику в табличном виде.

- $ vmstat -s

      4038844 K total memory
      1180932 K used memory
      1694344 K active memory
      542648 K inactive memory
      1403152 K free memory
      213312 K buffer memory
      1241448 K swap cache
      ...

#### **Команда top**

**top** — это утилита командной строки, которая используется для мониторинга процессов и используемых ресурсов компьютера.

Запуск утилиты **top** :

- $ top

В заголовке выводится информация об использованной оперативной памяти.      

#### **Команда htop**

Утилита **htop**, также как и **top**, используется для мониторинга ресурсов и процессов.

Для установки утилиты **htop** в Ubuntu Linux (Linux Mint и других Ubuntu/Debian-дистрибутивах) выполните команду:

- sudo apt install htop

Запуск утилиты htop:

- $ htop

#### Файл **/proc/meminfo**

Описанные выше команды, в качестве источника информации используют системные файлы из файлов, хранящихся в виртуальной файловой системе /proc. 

В файле /proc/meminfo содержится информация об использовании памяти.

 Выведем содержимое файла /proc/meminfo:

- cat /proc/meminfo

      MemTotal: 4038844 kB
      MemFree: 1341788 kB
      MemAvailable: 2474596 kB
      Buffers: 214128 kB
      Cached: 1065564 kB
      SwapCached: 0 kB
      Active: 1743700 kB
      ...

#### **Тип памяти и частота**

Рассмотрим, как получить информацию об установленных в компьютер модулях оперативной памяти. 

Воспользуемся командной **dmidecode**

Используем следующую команду:

sudo dmidecode --type 17

sudo dmidecode --type 17

\# dmidecode 3.1

Getting SMBIOS data from sysfs.

SMBIOS 2.4 present.

    Handle 0x0026, DMI type 17, 27 bytes
    Memory Device
    Array Handle: 0x0025
    Error Information Handle: Not Provided
    Total Width: 64 bits
    Data Width: 64 bits
    Size: 2048 MB
    Form Factor: DIMM
    Set: None
    Locator: A0
    Bank Locator: Bank0/1
    Type: DDR2
    Speed: 800 MT/s
    ...

В выводе команды будет информация о слотах оперативной памяти.

 Для каждого слота отображается установленный модуль оперативной памяти, его тип (поле Type), размер (поле Size), скорость/частота (поле Speed) и другая информация.

В зависимости от системы и оборудования не всегда удается получить все данные, поэтому некоторые поля могут быть пустыми или иметь надписи **Not provided/Unknown** .     
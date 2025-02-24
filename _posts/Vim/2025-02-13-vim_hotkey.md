---
layout: post
title:  Vim - keyboard shortcuts №1
category: vim
---

#### Самые главные команды:

- vim <'имя файла'>   -  открыть файл в терминале

- :q  -  выйти из vim(закрыть)

- :wq   -    записать(сохранить документ) и выйти

- :q!  -  выйти без сохранения

- :w  -  сохранить файл;

- :buffers - посмотреть открытые файлы.


#### *Это тоже может очень пригодится:*

Из внешнего документа скопировать текст - ctrl+c

и вставить в vim - ctrl+shift+v 

or

shift+insert(предпочтительнее)

из vim копировать в др.документ - shift+выделить текст

вставить в др.документе - нажать среднюю кнопку мыши или ctrl+v

***Работает в Ubuntu 20,Slackware 15,Trisquel 11 - точно!***

#### Перемещение по тексту(нормальный режим):

**h** -	Влево 

**l(L)** -	Вправо

**j** - 	Вниз

**k** - 	Вверх

**w** -	Вперед на первую букву слова

**e** -	Вперед на последнюю букву слова

**b** -	Назад на первую букву слова

**ge** -	Назад на последнюю букву слова

d - удалить символ;

dd - удалить всю строку;

D - удалить символы начиная от курсора и до конца строки;

y - копировать символ;

yy или Y - скопировать всю строку;

v - выделить текст;

p - вставить после позиции курсора;

P - вставить перед позицией курсора;

u - отменить последнее действие;

. - повторить еще раз последнее действие;

U - отменить последнее действие в текущей строке;

/ шаблон - искать вхождение;

%s/шаблон/заменить - заменить первое слово на второе;

n - продолжить поиск вперед;

N - продолжить поиск назад;

**W** - То, же, что и w, но словом считается то, что отделено пустыми символами

**E** -	То, же, что и e, но словом считается то, что отделено пустыми символами

**B** -	То, же, что и b, но словом считается то, что отделено пустыми символами

**gE** -	То, же, что и ge, но словом считается то, что отделено пустыми символами
^	На первый непустой символ строки

**$**, -  End	На конец строки

**0** - (ноль), Home	На начало строки

**(** -	На первую точку слева от курсора (если она есть, в противном случае на 
начало абзаца)

**)** -	На первую точку справа от курсора (если она есть, в противном случае на конец абзаца)

**{** -	На абзац назад до пустой строки

**}** -	На абзац вперед до пустой строки

**gj** -	На одну экранную строку вниз. Экранная строка — это целая строка длиной меньше ширины экрана, либо                                 часть длинной строки, разделенной на экране на несколько

**gk** -	На одну экранную строку вверх.

**f#** -	Поиск вперед в строке символа # и установка курсора на него

**F#** -	Поиск назад в строке символа # и установка курсора на него

**t#** -	Поиск вперед в строке символа # и установка курсора после него

**T#** -	Поиск назад в строке символа # и установка курсора после него

**;** -	Повтор поиска вперед символа, найденного при помощи f/t/F/T

**,** -	Повтор поиска назад символа, найденного при помощи f/t/F/T

**%** -	Перемещение курсора на скобку, парную той, на которой находится курсор

Парные символы можно задать при помощи команды;
 
**:set matchpairs**

**:№** -	Перемещение курсора на строку №...

**№G** -	Перемещение курсора на строку №..., аналогично :№...

**gg** -	Перемещение курсора в начало

**G** -	Перемещение курсора в конец

**№%** -	Перемещение курсора на №... процентов от начала

**H** -	Перемещение курсора на начало видимой части текста

**M** -	Перемещение курсора на середину видимой части текста

**L** -	Перемещение курсора на конец видимой части текста

**Control+u** -	На полэкрана вверх

**Control+d** -	На полэкрана вниз

**Control+y** -	На одну строку вверх. Курсор при этом не перемещается

**Control+e** -	На одну строку вниз. Курсор при этом не перемещается

**Control+b** -	На один экран минус 2 строки вверх

**Control+f** -	На одну экран минус 2 строки вниз

**zt** -	Прокрутка текста так, чтобы курсор оказался вверху экрана

**zz**	 -Прокрутка текста так, чтобы курсор оказался в середине экрана

**zb** -	Прокрутка текста так, чтобы курсор оказался внизу экрана

#### В обычном режиме:

*<<*	Сдвинуть строку влево (табуляция)
 
*>>*	Сдвинуть строку вправо (табуляция)

#### Режим выделения:

**v** -	Войти в режим выделения символов

**V** -	Войти в режим выделения строк

**Control+Shift+v** -	Войти в режим выделения прямоугольного блока текста

**gv** -	Выделяет текст, который был выделен предыдущей командой выделения

**o** -	Перемещение курсора в области блочного выделения для изменения размера влево

**O** -	Перемещение курсора в области блочного выделения для изменения размера вправо

**I** -	Включить вставку символов в блочном выделении. После нажатия I набираются символы, а по окончании нажимаете Escape. Все набранные символы будут вставлены в каждую строку

**с** -	Аналогично I, но перед вставкой символов удаляет всё, что было выделено блоком

**с** -	Аналогично I, но перед вставкой символов удаляет всё от левого края выделения до конца строки

**u** -	Изменить регистр выделенных символов на нижний

**U** -	Изменить регистр выделенных символов на верхний

**~** -	Изменить регистр выделенных символов на противоположный

**J** -	Объединить все строки, находящиеся в области выделения

**r** -	Заменить все символы на введенный после r, например rx заменит все символы в области выделения на x

**<** -	Сдвинуть выделенный блок влево (табуляция)

**>** - Сдвинуть выделенный блок вправо (табуляция)

#### Работа с буфером обмена:

**«*yy** -	Скопировать строку в буфер обмена текущего выделения. Потом можно вставить скопированное в любом приложении нажатием средней кнопки (колесика) мыши

**«+yy** -	Скопировать строку в буфер обмена. Потом можно вставить скопированное в любом приложении нажатием Ctrl+v

**«ayy** -	Скопировать строку в регистр a (имена регистров соответствуют буквам латинского алфавита, возможны имена a-z)

**«Ayy** -	Добавить строку в регистр a

**«ap** -	Вставить текст из регистра a

#### Вот основные команды для работы с буферами:

**:bn** - следующий буфер

**:bp** - предыдущий

**:ls** - просмотреть открытые буферы

**:b** -  имя_буфера переключиться на буфер, очень удобно комбинируется с табом, к примеру пишем **:b domain**, жмём таб и нам подставляется открытый **iis_domain.cpp**

**:bd** - удалить текущий буфер, правда стоит заметить, что если этот буфер единственное окно то **vim** закроется

**:bd** -  имя_буфера удалить буфер по имени

#### Метки:

**mx** -	Создать метку с именем x

**`x** -	Переместить курсор на метку x

**‘x** -	Переместить курсор на строку с меткой x

**:marks** -	Просмотреть все существующие в данный момент метки

**Ctrl+Shift+o** -	Перемещение по меткам назад

**Ctrl+Shift+i** -	Перемещение по меткам вперед

**‘ ‘** -	Переместить курсор на предыдущую метку

#### Поиск:

**/** -	Войти в режим ввода выражения для поиска. В vim можно использовать при поиске регулярные выражения, при этом символы «.», «*», «[«, «]», «^», «%», «/», «\», «?», «~», «$» являются специальными и их обязательно надо экранировать обратным слэшем («\»)

**noh** - выйти из режима поиска,выключит подсветку найденого.

**?** -	То же, что и /, но поиск будет производиться в обратном порядке

**n** -	Повторить поиск вперед

**N** -	Повторить поиск назад

**(*)** -	Поиск слова, на котором стоит курсор, вперед, со строгим соответствием(звездочка без скобок)

**#** -	Поиск слова, на котором стоит курсор, назад, со строгим соответствием

**(g*)** -	Поиск слова, на котором стоит курсор, вперед, с нестрогим соответствием, то есть, если курсор на слове win, то будет найдено также слово winter

**g#** -	Поиск слова, на котором стоит курсор, назад, с нестрогим соответствием
/выражение\c	Поиск слова без учета регистра, независимо от настроек **vim**. Переключать учет регистра можно командами «:**set ignorecase» и «:set noignorecase**»

**\<** -	Обозначение начала слова при поиске. /\

** \>** -	Обозначение конца слова при поиске. **win** — найти только /\<win\>., но не **winter**

**/выражение/b+1** -	Найти выражение и установить курсор на символ +1 от начального, то есть на второй

**/выражение/e-3** -	Найти выражение и установить курсор на символ -3 от конечного

**?выражение?b+1** -	То же, что и /выражение/b+1, но с поиском в обратную строну

**?выражение?e-3** -	То же, что и /выражение/e-3, но с поиском в обратную строну
стрелка вверх	При вводе строки для поиска просмотр истории поиска выражений, начинающихся с того, что уже набрано

#### Давайте подытожим список основных команд, используемых при работе с окнами в Vim.

**:split** или **Ctrl+w s** — добавляет в сессию Vim горизонтальное окно

**:vsplit** или **Ctrl+w v** — добавляет в сессию Vim вертикально окно

**:split filename**  — добавляет в сессию Vim горизонтальное окно и загружает в него filename

**:vsplit filename**  — добавляет в сессию Vim вертикальное окно и загружает в него filename

**Ctrl+w h**— переключает на левое окно, относительно текущего

**Ctrl+w l** — переключает на правое окно, относительно текущего

**Ctrl+w j** — переключает на нижнее окно, относительно текущего

**Ctrl+w k** — переключает на верхнее окно, относительно текущего

**Ctrl+w** **Ctrl+w** — переключает на следующее окно

**Ctrl+w r** — передвигает окна по часовой стрелке

**Ctrl+w R** — передвигает окна против часовой стрелки

**Ctrl+w c** — закрывает текущее окно

**Ctrl-w стрелочки :)** — переместиться на окно влево/вправо/вверх/вниз

**Сtrl-w o** — развернуть окно

**Ctrl-w c** — закрыть

**Ctrl-w s** — разделить окно по горизонтали

**Ctrl-w v** — тоже, только по вертикали

**Ctrl+w +** — увеличение размера окна по горизонтали;

**Ctrl+w —** — уменьшение размера окна по горизонтали;

**Ctrl+w >** — увеличение размера окна по вертикали;

**Ctrl+w <** — уменьшение размера окна по вертикали;

**Ctrl-w ]** — разделить и перейти на определение чего-то, что под курсором

**Ctrl-w f** — разделить и в новом окне открыть файл путь к которому находится под курсором, очень удобно делать на инклюдах

#### Команды:

**:split** — разделить, если указан файл то открыть его

**:vsplit** — тоже только по вертикали

**:sb[uffer**] — разделить и редактировать буффер. Важный момент: если заново открыть файл (к примеру через **:split**) то буфер сбрасывается, вместе с историей отмен и положением курсора


#### Давайте подытожим список команд для работы с вкладками:

**vim -p filename1 filename2** — запустит **Vim** и откроет (или создаст новые) файлы **filename1** и **filename2**  в двух вкладках

**:tabnew** — откроет пустую вкладку

**:tabnew filename**— откроет новую вкладку и загрузит (создаст новый) в ней файл filename

**gt** — переключит на следующую вкладку

**gT** — переключит на предыдущую вкладку

**:tabc** — закроет текущую вкладку


И так, буфер это некий сеанс редактирования определённого файла.

К примеру если вы открыли **.vimrc** и в запущенном виме выполнили **:e .bashrc**, то откроется **.bashrc**.

Тем не менее буфер с **.vimrc** останется открытым и доступным для редактирования.



#### ОДНОВРЕМЕННОЕ РЕДАКТИРОВАНИЕ НЕСКОЛЬКИХ ФАЙЛОВ

Чтобы открыть несколько файлов, просто передайте их в параметры при запуске программы:

 vim файл1 файл2 файл3

Редактор vim linux откроет первый файл, для переключения ко второму используйте команду :n, чтобы вернутся назад :N.

С помощью команды :buffers вы можете посмотреть все открытые файлы, а командой :buffer 3 переключится на третий файл.

#### БУФЕР ОБМЕНА VIM

Текстовый редактор Vim имеет свой буфер обмена. Например, вам нужно скопировать в четыре строки и вставить их в другое место программы, для этого выполните такую последовательность действий:

• Нажмите Esc, чтобы перейти в командный режим;

• Наберите 4yy чтобы скопировать четыре строки;

• Переместите курсор в место где нужно вставить эти строки;

• Нажмите p для вставки.

Также можно использовать выделение vim, чтобы скопировать строки. Выделите текст с помощью v, а затем нажмите y, чтобы скопировать.

#### КИРИЛЛИЦА В VIM

Кириллица в Vim работает превосходно. Но есть одно но, когда включена кириллица в системе, все команды vim не работают, им и не нужно работать, они же не приспособлены для кириллицы.
Но переключать каждый раз раскладку, когда работаете в командном режиме тоже не очень удобно.

открываем файл ~/.vimrc и добавляем туда такие строки:

set keymap=russian-jcukenwin

set iminsert=0

set imsearch=0



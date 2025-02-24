---
layout: post
title:  Emacs.Org-mode.
category: Other
---

### В emacs есть замечательный режим org-mode.

#### Он исползуется для организации заметок,и не только.

**\#+STARTUP: content (начало документа или другой из следующих ниже)**

#### *режимы открытия org-mode*

- +STARTUP: overline (все свернуто)

- +STARTUP: content  (все содержимое)

- +STARTUP: showall  (все деревья)

- +STARTUP: showeverything (все,дроиры,записки,содержимое,деревья)
 

#### *Visibility cycling (начальный вид заметок)*

- Tab – show current (показывать текущий)

- S-tab – show all children (показать все заметки)

- C-u C-u C-u Tab – show all including drawers (показать все, включая 'выдвижные ящики')


#### Startup options

***Editting (создание,удаление,редактирование вкладок)***

#### M - (Meta key) || ALT - key

- M-Ret – add element on the same level(добавить элемент на том же уровне)

- M-S-Ret – insert TODO element

- M-Right – demote current element(понизить текущий элемент в уровне)

- M-S-Right – deomote current subtree

- M-Left – promote current element(повысить текущий элемент в уровне)

- M-S-Left – promote current subtree

- M-S-Up – move current tree up

- M-S-Down – move current tree down

- C-c C-x C-w – kill current subtree

- C-c C-x M-w – copy current subtree

- C-c C-x C-y – yank subtree

*Plain lists (Простые списки)

***Use M-Ret to add list item***

#### Ordered list:

    1. First
    2. Second
    3. Third

#### *Unordered lists*

    abc
    efg

#### *List with checkboxes (M-S-Ret) (создание чек-боксов)*

    [ ] First element
    [X] Second element (C-c C-c – toggle checkbox state)
    [X] Third element

#### *More devices*

- C-c C-z – time-stamped drawer

    >Note taken on [2013-09-02 Mon 23:54]
    >
    >My note here

- C-c C-x f – footnote

#### *ToDo functionality*

- C-c C-t – rotate TODO state

- S-Left, S-Right – rotate TODO state

- S-M-Ret – insert new TODO note

- (setq org-todo-keywords’((sequence “TODO” “FEEDBACK” “VERIFY” “|” “DONE” “DELEGATED”)))

#### *Footnotes*

- [fn:1] The footnote.

- [fn:2] Second footnote.

#### *HTML export commands (создание HTML страницы)*

- C-c C-e h h (org-html-export-to-html)

    Export as HTML file with a ‘.html’ extension. For ‘myfile.org’, Org exports to ‘myfile.html’, overwriting without warning. {{{kbd{C-c C-e h o)}}} exports to HTML and opens it in a web browser.
    
- C-c C-e h H (org-html-export-as-html)

    Exports to a temporary buffer. Does not create a file. 
	
 
#### *Org export commands*

- C-c C-e O o (org-org-export-to-org)

    Export as an Org file with a ‘.org’ extension. For ‘myfile.org’, Org exports to ‘myfile.org.org’, overwriting without warning.

- C-c C-e O v (~~)

#### *Export to an Org file, then open it* 
	
#### *note* 

- c - c; c - z -  создать todo

- c - c; c - c  - сохранить todo

- c - c; c - k  - удалить todo

#### *footnote*

c - c; c - x; f  - создать footnote

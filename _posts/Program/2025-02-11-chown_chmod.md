---
layout: post
title: Права доступа для файлов и директорий
category: Program
---

### Работа с правами доступа файлов и директорий в Linux

---

- \# chown vasya /file

Назначить пользователя vasya владельцем файла file

---

- \# chown -R vasya directory

Рекурсивно обойти директорию directory и назначить пользователя 
vasya владельцем всех вложенных файлов и директорий

---

- \# chown vasya:group /file

Назначить владельца и группу для файла /file

---

- \# chmod ugo+rwx /directory

Установить полные права доступа rwx ( Read Write eXecute ) для всех ugo ( User Group Other ) на директорию /directory. То-же самое можно сделать, используя числовой представление chmod 777 directory

---

- \# chmod go-rwx /directory

Удалить все права на директорию /directory для группы и остальных

---

- \# chgrp new_group file

Изменить группу-владельца для file на new_group

---

- \# chmod o+t /home/public

Установить так называемый STIKY-бит на директорию /home/public. Удалить файл в такой директории может только владелец данного файла

---

- \# chmod o-t /home/public

Удалить STIKY-бит с директории /home/public

---

- \# chmod u+s /bin/binary_file

Установить SUID-бит на файл /bin/binary_file. Это позволяет любому пользователю системы, запускать данный файл с правами владельца файла

---

- \# chmod u-s /bin/binary_file

Удалить SUID-бит с файла /bin/binary_file

---

- \# chmod g+s /home/public

Установить SGID-бит на директории /home/public

---

- \# chmod g-s /home/public

Удалить SGID-бит с директории /home/public

---

- \# find / -perm -u+s

Поиск всех файлов с установленным SUID битом, начиная с корня файловой системы

---

- \# ls -lh

Листинг текущего каталога с правами доступа

---


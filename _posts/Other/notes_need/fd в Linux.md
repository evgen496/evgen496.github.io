#### Как использовать fd в Linux?

Подобно команде **find**, **fd** имеет множество вариантов использования, но давайте начнем с проверки доступных опций:

\# fd -h

Или

\# fd --help

[![fd-Command-Usage](https://blog.sedicomm.com/wp-content/uploads/2019/04/fd-Command-Usage.png)](https://blog.sedicomm.com/wp-content/uploads/2019/04/fd-Command-Usage.png)

Давайте рассмотрим несколько примеров. Можно запускать **fd** без аргументов, вывод очень похож на команду **ls -R**.

\# fd

В следующих примерах fd я буду использовать стандартную версию **WordPress**, расположенную в **/var/wwww/html/** для поиска различных файлов и папок.

В примере ниже я взял только первые 10 результатов для более короткого вывода команды:

\# fd | head

![](https://blog.sedicomm.com/wp-content/uploads/2019/05/izobrazhenie_2021-06-06_215937.png)

Допустим, мы хотим найти все **jpg** файлы. Мы можем использовать флаг “**-e**” для фильтрации по расширению файла:

\# fd -e jpg

![](https://blog.sedicomm.com/wp-content/uploads/2019/05/izobrazhenie_2021-06-06_220030.png)

Пример мой:
```
[jenit@host-102 ~]$ fd solnce2.mp3
Музыка/solnce2.mp3
```

Флаг “**-e**” может быть использован в сочетании с подобным шаблоном:

\# fd -e php index

Вышеприведенная команда будет искать файлы с расширением **php** в которых 
есть строка “**index**“:

Если вы хотите исключить некоторые результаты, вы можете использовать флаг “**-E**” следующим образом:

\# fd -e php index -E wp-content

Эта команда будет искать все файлы с расширением **php**, содержащие строку “**index**” и исключит результаты из директории “**wp** **Content**“.

Если вы хотите указать каталог поиска, вам просто нужно привести его в качестве аргумента:

\# fd \<pattery> \<directory>

Как и для команды **find**, вы можете использовать аргументы **-x** или **-exec** для выполнения параллельных команд с результатами поиска.

Вот пример, где мы будем использовать **chmod** для изменения разрешений файлов изображений.

\# fd -e jpg -x chmod 644 {}

Приведенные выше файлы с расширением **jpg** будут найдены и запущены под управлением **chmod 644 <path-to-file>**.

Вот некоторые объяснения использования скобок:

- **{}** – заполнитель, который будет изменен в ходе выполнения к результату поиска (**wp-content/uploads/01.jpg**).
- **{.}** – аналогично **{}**, но без использования расширения файла (**wp-content/uploads/01**).
- **{/}** – заполнитель, который будет заменен на базовое имя результата поиска (**01.jpg**).
- **{//}** – родительский каталог найденного пути (**wp-content/uploads**).
- **{/.}** – только базовое имя, без расширения (**01**).

#### Заключение

Это был краткий обзор команды **fd**, которая очень проста в использовании. Как упоминалось ранее в этой статье, **fd** не предназначена для полной замены **find**, а скорее обеспечивает простоту поиска и лучшую производительность. **Fd** не занимает много места и является хорошим инструментом в вашем арсенале.
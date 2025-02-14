---
layout: post
title: Планировщик заданий. Автоперезагрузка
category: Linux
---

#auto #cron #autocron #reboot #root

- \# shutdown -r 18:00

#### распишу на всякой

- sudo crontab -e

- 0 5 * * * /sbin/reboot
  

#### В crontab дни недели задаются с помощью символов «*».

Возможные значения: 0–7

Символ «*» в поле дня недели означает «каждый день недели»

Можно указывать конкретные значения, разделяя их запятыми

Например, «1,3,5» означает «в понедельник, среду и пятницу»

[nic.ru](https://www.nic.ru/help/gid-po-nastrojke-cron-zadaniya-na-vydelennom-servere_11621.html)

---

#### В crontab поле "День недели" запускается из 0 - 6 или 1 -7?

0 и 7 оба обозначают воскресенье, вы можете использовать тот, который хотите, поэтому запись 0-6 или 1-7 приведет к тому же результату.

- 0 - Sun Sunday

- 1 - Mon Monday

- 2 - Tue Tuesday

- 3 - Wed Wednesday

- 4 - Thu Thursday

- 5 - Fri Friday

- 6 - Sat Saturday

- 7 - Sun Sunday

---

Графически * * * * * command to be executed означает:
```
|минута|час|день месяца|месяц|день недели||
|---|---|---|---|---|---|
|(0-59)|(0-23)|(1-31)|(1-12)|(1-7)||
|*|*|*|*|*|команда, которая должна быть выполнена|
```
Или использовать старый стиль:

  
```
┌────────── minute (0 - 59)

│ ┌──────── hour (0 - 23)

│ │ ┌────── day of month (1 - 31)

│ │ │ ┌──── month (1 - 12)

│ │ │ │ ┌── day of week (0 - 6 => Sunday - Saturday, or

│ │ │ │ │ 1 - 7 => Monday - Sunday)

↓ ↓ ↓ ↓ ↓

* * * * * command to be executed
```
  

Наконец, если вы хотите указать день за днем, вы можете разделять дни запятыми, например, SUN,MON,THU будет выполняться команда только по воскресеньям, с понедельника по четверг.

Более подробную информацию вы можете прочитать в:

[статье Википедии о Cron](https://translated.turbopages.org/proxy_u/en-ru.ru.ea56643f-66b1e25b-12383f80-74722d776562/https/en.wikipedia.org/wiki/Cron) и проверить выражение cron онлайн с помощью [crontab.guru](https://translated.turbopages.org/proxy_u/en-ru.ru.ea56643f-66b1e25b-12383f80-74722d776562/https/crontab.guru/).

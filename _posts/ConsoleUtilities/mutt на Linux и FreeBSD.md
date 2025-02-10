## mutt на Linux и FreeBSD

### Настройка клиента

Рассмотрим принцип настройки клиента Mutt для работы по IMAP и POP3.

### IMAP + SMTP

Открываем конфигурационный файл:

vi ~/.muttrc

И приводим его к следующему виду:

set from = master@dmosk.ru
set imap_user = master@dmosk.ru
set imap_pass = password
set smtp_pass = password
set realname = "Дмитрий Моск"
set smtp_url = smtp://smtp.dmosk.ru:465/
set folder = imaps://imap.dmosk.ru:993

set spoolfile = +INBOX
set postponed = +[Gmail]/Drafts

set use_from = yes
set editor='nano'
set sort = reverse-threads
set sort_aux = last-date-received

set fast_reply=yes
set include=yes
set forward_quote=yes
set delete=yes

set imap_keepalive  = 900
set copy = no
set move = no

set header_cache    = ~/.mutt/cache/headers
set message_cachedir    = ~/.mutt/cache/bodies
set certificate_file    = ~/.mutt/certificates

set ssl_starttls = yes
set ssl_force_tls = yes
set smtp_authenticators = 'login'

* где необходимо обратить внимание на следующие опции:

    master@dmosk.ru — адрес электронной почты; Используем для поля from и в качестве логина.
    master — имя учетной записи;
    password — пароль;
    Дмитрий Моск — отображаемое имя;
    smtp.dmosk.ru — SMTP-сервер; В данном примере мы подключаемся к серверу по SSL-порту 465. Также могут быть варианты 587 и 25.
    imap.dmosk.ru — сервер IMAP. Подключение выполняем по SSL-порту 993. Также можно использовать порт 143.

Для проверки вводим команду:

mutt

При запросе подтвердить принятие сертификата, нажимаем a.

### POP3 + SMTP

Открываем конфигурационный файл:

vi ~/.muttrc

И приводим его к следующему виду:

set from = master@dmosk.ru
set smtp_pass = password
set realname = "Дмитрий Моск"
set smtp_url = smtp://smtp.mail.ru:465/

set pop_user = master@dmosk.ru
set pop_pass = password
set pop_host = pops://pop.dmosk.ru:995/
set pop_reconnect = yes
set pop_checkinterval = 1
set pop_delete = no

set mbox_type = mbox
set folder = ~/mail
set mbox = +Inbox
set spoolfile= +Inbox

set use_from = yes
set editor='nano'
set sort = reverse-threads
set sort_aux = last-date-received

set fast_reply=yes
set include=yes
set forward_quote=yes
set delete=yes

set imap_keepalive  = 900
set copy = no
set move = no

set header_cache    = ~/.mutt/cache/headers
set message_cachedir    = ~/.mutt/cache/bodies
set certificate_file    = ~/.mutt/certificates

set ssl_starttls = yes
set ssl_force_tls = yes
set smtp_authenticators = 'login'

* где необходимо обратить внимание на следующие опции:

    master@dmosk.ru — адрес электронной почты; Используем для поля from и в качестве логина.
    master — имя учетной записи;
    password — пароль;
    Дмитрий Моск — отображаемое имя;
    smtp.dmosk.ru — SMTP-сервер; В данном примере мы подключаемся к серверу по SSL-порту 465. Также могут быть варианты 587 и 25.
    imap.dmosk.ru — сервер IMAP. Подключение выполняем по SSL-порту 993. Также можно использовать порт 143.

Для проверки вводим команду:

mutt

При запросе подтвердить принятие сертификата, нажимаем a.
Примеры настройки для разных почтовых систем

### Яндекс

По умолчанию, доступ на Яндекс из почтовых клиентов закрыт. Необходимо зайти на почту в браузере, кликнуть по значку шестеренки - Все настройки - Почтовые программы - Включить «С сервера imap.yandex.ru по протоколу IMAP». Подробнее в инструкции Настройка почты GMAIL и Яндекс для подключения по IMAP или POP3.

Далее создаем файл с настройкой mutt:

vi ~/.muttrc

set realname = "Дмитрий Моск"
set from = username@yandex.ru
set use_from = yes

set imap_user = username@yandex.ru
set imap_pass = password
set smtp_url = smtp://smtp.yandex.ru:465/
set smtp_pass = password
set smtp_authenticators = 'login'

set ssl_starttls = yes
set ssl_force_tls = yes

set folder = imaps://imap.yandex.ru:993
set spoolfile = +INBOX
set postponed = +[Gmail]/Drafts
set record = =Отправленные

### @Mail.ru

vi ~/.muttrc

set realname = "Дмитрий Моск"
set from = username@mail.ru
set use_from = yes

set imap_user = username@mail.ru
set imap_pass = password
set smtp_url = smtp://smtp.mail.ru:465/
set smtp_pass = password
set smtp_authenticators = 'login'

set ssl_starttls = yes
set ssl_force_tls = yes

set folder = imaps://imap.mail.ru:993
set spoolfile = +INBOX
set postponed = +[Gmail]/Drafts
set record = =Отправленные

### GMAIL

Как в случае с Яндексом, в GMAIL также необходимо включить поддержку imap. Для этого заходим в настройки почты (кликаем по значку шестеренки) - Настройки - Пересылка и POP/IMAP - Включить IMAP.

На этом не все — Google требует безопасную аутентификацию OAuth2. Чтобы у нас заработал Mutt, необходимо разрешить подключение с устаревших приложений. Для этого заходим в настройки общего аккаунта Google - Безопасность - прокручиваем до «Ненадежные приложения, у которых есть доступ к аккаунту» - кликаем по Открыть доступ (не рекомендуется) - меняем положение переключателя «Небезопасные приложения заблокированы» на положение «включено».

Подробнее о включении IMAP и POP3 для почты от Google читайте в инструкции Настройка почты GMAIL и Яндекс для подключения по IMAP или POP3.

vi ~/.muttrc

set realname = "Дмитрий Моск"
set from = username@gmail.com
set use_from = yes

set imap_user = username@gmail.com
set imap_pass = password
set smtp_url = smtp://smtp.gmail.com:465/
set smtp_pass = password
set smtp_authenticators = 'login'

set ssl_starttls = yes
set ssl_force_tls = yes

set folder = imaps://imap.gmail.com:993
set spoolfile = +INBOX
set postponed = +[Gmail]/Drafts
set record = =Отправленные
Отправка почты из консоли

Для быстрой отправки почты из командной строки можно воспользоваться Mutt. Для этого используем приложение со следующим синтаксисом:

echo "Текст сообщения" | mutt -s "Тема" [дополнительные опции] -- <кому отправить>

Пример:

echo "Test mail" | mutt -s "Mutt subject" -- master@dmosk.ru

* в данном примере мы отправим письмо на электронный адрес master@dmosk.ru с темой Mutt subject и содержимым Test mail.

Взято:

https://www.dmosk.ru/miniinstruktions.php?mini=mutt

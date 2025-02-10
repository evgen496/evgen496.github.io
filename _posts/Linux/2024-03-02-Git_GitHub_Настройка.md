---
layout: post
title: Настройка Git и GitHub на линукс
category: Linux
---

Шаг 1: Убедитесь, что у вас установлен Git на вашем Linux-устройстве.

Если нет, выполните следующую команду:

- sudo apt-get install git

Шаг 2: Когда Git установлен, следующим шагом является настройка вашего имени пользователя и адреса электронной почты.

Выполните следующие команды, заменив "Your Name" и "your@email.com":

- git config —global user.name "Your Name"

- git config —global user.email "your@email.com"

Шаг 3: Прежде чем мы начнем использовать Git, нам нужно создать новый репозиторий на GitHub. Зайдите на сайт GitHub, войдите в свою учетную запись и нажмите кнопку "New repository".

Шаг 4: Теперь, когда есть репозиторий на GitHub, свяжем его с нашим локальным Git-репозиторием. Перейдите в каталог вашего проекта и выполните следующие команды:

- git init

- git remote add origin https://github.com/username/repository.git

Здесь "username" - ваше имя пользователя на GitHub, а "repository" - название вашего репозитория.

---

Клонируем репозиторий на свой комп

- git clone https://github.com/user/user.github.io

Идём туда(папку) и смотрим что там.

Что то правим,добавляем.

Отправляем в Git репозиторий:

- git add .

- git commit -m "new"

- git push -u origin main

или

- git push

user:  % Ваш логин на github

Password for(token): % получить его можно в Settings>DeveloperSettings>PersonalAccesToken ,сгенерировать ключ и копипаст вместо пароля

[Как получить токен(пароль)](https://vk.com/wall-215896332_192)



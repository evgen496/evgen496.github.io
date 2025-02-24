---
layout: post
title:   В VS Code устанавливаем LaTex Workshop
category: LaTeX
---

В VS Code устанавливаем LaTex Workshop

1. Запускаем VS code. Создаём файл (Ctrl + N -> select language -> latex) с раширеним .tex и записываем в него код

2. Нажимаем Ctrl + Alt + B , ждём пока всё соберётся (это может занять пару минут, так как MikTex устанавливает необходимые пакеты).

3. Нажимаем Ctrl + A + V и должно появиться окошко для отображения нашего текста. Наведите курсор на математическую формулу и нажмите Ctrl+Alt+M.
И, наконец Ctrl+Shift+P -> напишите: "Latex: Focus on Snippet View"

## Обобщение

- Устанавливаем VS Code

- Устанавливаем LaTeX

- Устанавливаем расширение для VS Code - LaTeX Workshop

- Устанавливаем расширение для VS Code - HyperSnips

- Настраиваем сниппеты в LaTeX Workshop

- Настраиваем сниппеты в HyperSnips

- Устанавливаем и настраиваем программу для удобной смены раскладки

**Пользуемся**

*Ссылка на готовые сниппеты в конце статьи.*

Далее идёт объяснение того, как это работает. Вы можете пользоваться этим текстом по мере того, пока самостоятельно (ведь так интереснее) осваиваете все сниппеты.

### Сниппеты

```Сниппеты - это команды, сокращения текста, позволяющие быстро печатать большие объёмы текста.```

Например, для набора дроби в LaTeX Вам нужно ввести что-то наподобие "\frac{a}{b}", что в итоге даст нам \frac{a}{b}. Согласитесь, неудобно вводить этот текст напрямую. Благодаря сниппетам, можно сделать команду, чтобы при наборе "a/" текст заменялся на "\frac{a}{}", а курсор устанавливался внутри вторых фигурных скобок, чтобы написать знаменатель. Более того, чтобы выйти из внутренностей текста, часто оказывается удобным использование tab. То есть Вы можете настроить сниппет таким образом, чтобы при нажатии tab курсор устанавливался в конец вставленного текста.
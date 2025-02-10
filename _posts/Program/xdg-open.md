команда xdg-open в системе Linux используется для открытия файла или URL-адреса в предпочтительном приложении пользователя. URL-адрес будет открыт в предпочтительном веб-браузере пользователя, если указан URL-адрес. Файл будет открыт в предпочтительном приложении для файлов этого типа, если файл предоставлен. поддержка xdg-open ftp, файл, https, и http URL-адреса.

Она является частью пакета XDG Utils и служит методом независимого от среды открытия файлов в приложениях. Команда полезна для интеграции со сценариями или другими командами в системе, которая требует открытия документа или подключения к URL-адресу непосредственно из командной строки.

Это можно использовать только в сеансе рабочего стола. Не рекомендуется использовать xdg-open от имени root. Здесь ноль указывает на успех, в то время как ненулевое значение указывает на сбой.

Синтаксис

xdg-open {file | URL}

где,

    file: Указывает файл, который вы хотите открыть.
    
    URL: Указывает URL, который вы хотите открыть.

Examples

    Opening a PDF File:

    xdg-open example.pdf

    This command opens example.pdf using the system’s default PDF viewer.

    Opening a URL:

    xdg-open https://www.example.com

    This will open the specified URL in the user’s default web browser.
    
[Desktop Entry]
Name=Discord (web version)
Name[ru]=Дискорд (веб-версия)
StartupWMClass=discord
Comment=Launching Discord via the browser.
Comment[ru]=Запуск Дискорд через браузер.
GenericName=Internet Messenger
Exec=xdg-open https://discord.com/channels/378683352946835456/979455678273966220
Icon=discord
Type=Application
Categories=Network;InstantMessaging;    

/home/jenit/.local/share/applications/
/usr/local/share/applications/


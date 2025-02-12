---
layout: post
title:   Beamer. Изменить фон слайда
category: LaTeX_Beamer
---

#beamer #back #slid #слайд
  
Если вам хочется изменить фон слайда, воспользуйтесь командой \usebackgroundtemplate, внутри которой могут быть любые латеховские инструкции (в т.ч. и размещение изображения). Например, мы можем поместить фоном всего кадра картинку:  
  
```
\usebackgroundtemplate{\includegraphics[width=\paperwidth,height=\paperheight]{penguin.jpg}}
```

Изменяйте фоновое полотно перед началом кадра, а не внутри кадра.


Поместите команду за пределы кадра. Это приведет к изменению цвета фона для каждого последующего кадра. Если вы хотите просто изменить этот слайд, вы можете заключить рамку и команду в `\setbeamercolor``{}`

Вот полный пример:

```latex
\documentclass{beamer}
\begin{document}
\begin{frame}{A white frame}
\end{frame}
% Change all subsequent frames to violet
\setbeamercolor{background canvas}{bg=violet!20}
\begin{frame}{A violet frame}
\end{frame}
\begin{frame}{This frame is also violet}
\end{frame}
% But this frame only will be yellow: note { ... } around
% the \setbeamercolor and the frame to limit the scope 
{\setbeamercolor{background canvas}{bg=yellow!20}
\begin{frame}{This frame is yellow}
\end{frame}
}
\begin{frame}{Subsequent frames will be violet}
\end{frame}
\end{document}
```

[![Вывод кода](https://i.sstatic.net/2OUa7.png)](https://i.sstatic.net/2OUa7.png)
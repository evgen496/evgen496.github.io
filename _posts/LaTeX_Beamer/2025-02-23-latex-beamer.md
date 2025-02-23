---
layout: post
title:   Beamer. Преамбула.
category: LaTeX_Beamer
---

#### Меня всем устраивает Madrid с добавлением шрифтов DejaVu

\documentclass[pdf,9pt,aspectratio=43]{beamer}
\usepackage[utf8x]{inputenc}
\usepackage{DejaVuSans}
\usepackage{DejaVuSerif}
\usepackage{DejaVuSansMono}
\usepackage[T2A]{fontenc}
\usepackage[russian]{babel}
\usepackage{hyperref}
\hypersetup{unicode=true}

\usetheme{Madrid}
\usefonttheme[stillsansserifsmall]{serif}
\usefonttheme[onlylarge]{structureitalicserif}
---
## Front matter
title: "Лабораторная работа №3"
subtitle: "Моделирование стохастических процессов"
author: " Акопян Сатеник "

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью данной лабораторной работы является освоить первоначальные знания по моделированию стохастических процессов.

# Теоретическое введение

Здесь описываются теоретические аспекты, связанные с выполнением работы.
$M |M |1$ — однолинейная СМО с накопителем бесконечной ёмкости. Поступаю-
щий поток заявок — пуассоновский с интенсивностью $λ$. Времена обслуживания
заявок — независимые в совокупности случайные величины, распределённые по
экспоненциальному закону с параметром $μ$.


$M |M |n|R$ — однолинейная СМО с накопителем конечной ёмкости R. Поступаю-
щий поток заявок — пуассоновский с интенсивностью $λ$. Времена обслуживания
заявок — независимые в совокупности случайные величины, распределённые по
экспоненциальному закону с параметром $μ$.

# Выполнение лабораторной работы

1. Реализация модели на NS-2 (рис. [-@fig:001]).

![рисунок 1](image/1.png){#fig:001 width=70%}

2. Запускем модель, получаем теоретическую вероятность потери и теоретическую длину очереди (рис. [-@fig:002]).

![рисунок 2](image/3.png){#fig:002 width=70%}

3. В каталоге с проектом создаю отдельный файл, graph_plot, делаю его исполняемым (рис. [-@fig:003]):

![рисунок 3](image/2.png){#fig:003 width=70%} 

![рисунок 4](image/4.png){#fig:004 width=70%} 

4. Запускаю скрипт в созданном файле graph_plot, который создает файл файл qm.pdf с результатами моделирования (рис. [-@fig:005])

![рисунок 5](image/5.png){#fig:005 width=70%} 

![размер очереди в пакетах](image/6.png){#fig:006 width=70%} 

![приближение сплайном](image/7.png){#fig:007 width=70%} 

![приближение Безье](image/8.png){#fig:008 width=70%} 

# Выводы

В результате данной лабораторной работы я освоила первоначальные знания по моделированию стохастических процессов.

# Список литературы{.unnumbered}

::: {#refs}
:::

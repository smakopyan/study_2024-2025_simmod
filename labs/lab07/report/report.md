---
## Front matter
title: "Лабораторная работа 7"
subtitle: "Модель $M |M |1|∞$"
author: "Акопян Сатеник"

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

Смоделировать в xcos системы массового обслуживания типа M |M |1|∞

# Выполнение лабораторной работы

Зафиксируем начальные данные: $λ = 0, 3, μ = 0, 35, z_0 = 6$. Суперблок, моделирующий поступление заявок, представлен на (рис. [-@fig:001]).

![Суперблок, моделирующий поступление заявок](image/2.png){#fig:001 width=70%}

Суперблок, моделирующий процесс обработки заявок, представлен на (рис. [-@fig:002]).

![ Суперблок, моделирующий обработку заявок](image/3.png){#fig:002 width=70%}

Готовая модель $M |M |1|∞$ представлена на  (рис. [-@fig:003]).

![Модель $M |M |1|∞$ в xcos](image/4.png){#fig:003 width=70%}

Результат моделирования представлен на (рис. [-@fig:004], [-@fig:005]).

![Поступление и обработка заявок](image/5.png){#fig:004 width=70%}

![Динамика размера очереди](image/6.png){#fig:005 width=70%}


# Выводы

В результате данной лабораторной работы была смоделирована модель системы массового обслуживания типа $M |M |1|∞$ в xcos 

---
## Front matter
title: "Лабораторная работа №2"
subtitle: "Исследование протокола TCP и алгоритма управления очередью RED"
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

Исследование протокола TCP и алгоритма управления очередью RED.

# Задание

Описание моделируемой сети:

– сеть состоит из 6 узлов;

– между всеми узлами установлено дуплексное соединение с различными пропуск-
ной способностью и задержкой 10 мс;

– узел r1 использует очередь с дисциплиной RED для накопления пакетов, макси-
мальный размер которой составляет 25;

– TCP-источники на узлах s1 и s2 подключаются к TCP-приёмнику на узле s3;

– генераторы трафика FTP прикреплены к TCP-агентам.

Требуется разработать сценарий, реализующий модель согласно, по-
строить в Xgraph график изменения TCP-окна, график изменения длины очереди
и средней длины очереди

# Теоретическое введение

Протокол управления передачей (Transmission Control Protocol, TCP) имеет средства управления потоком и коррекции ошибок, ориентирован на установление
соединения.

Oбъект мониторинга очереди оповещает диспетчера очереди о поступлении пакета.
Диспетчер очереди осуществляет мониторинг очереди.

# Выполнение лабораторной работы

1. Создается файл tcp.tcl на основе шаблона shablon.tcl c реализацией модели (рис. [-@fig:001], [-@fig:002], [-@fig:003]).

![рисунок 1](image/1.png){#fig:001 width=70%}

![рисунок 2](image/2.png){#fig:002 width=70%}

![рисунок 3](image/3.png){#fig:003 width=70%}

Графики окна TCP и очереди (рис. [-@fig:004], [-@fig:005])

![рисунок 4](image/4.png){#fig:004 width=70%}

![рисунок 5](image/5.png){#fig:005 width=70%}

2. Измените в модели на узле s1 тип протокола TCP с Reno на NewReno, затем на
Vegas. (рис. [-@fig:006])

Меняем  TCP/Reno -> TCP/Newreno

![рисунок 6](image/9.png){#fig:006 width=70%}

![рисунок 7](image/8.png){#fig:007 width=70%}


Меняем  TCP/Reno -> TCP/Vegas (рис. [-@fig:008])

![рисунок 8](image/10.png){#fig:008 width=70%}

![рисунок 9](image/11.png){#fig:009 width=70%}

![рисунок 10](image/12.png){#fig:010 width=70%}

3. Внесите изменения при отображении окон с графиками (измените цвет фона,
цвет траекторий, подписи к осям, подпись траектории в легенде)

Поменяла red -> red!!!! (рис. [-@fig:011])

![рисунок 11](image/13.png){#fig:011 width=70%}

![рисунок 12](image/14.png){#fig:012 width=70%}

Поменяла цвета траекторий: (рис. [-@fig:013])

![рисунок 13](image/15.png){#fig:013 width=70%}

![рисунок 14](image/16.png){#fig:014 width=70%}


# Выводы

В результате данной лабораторной работы я исследовала протокол TCP и алгоритм управления очередью RED.

# Список литературы{.unnumbered}

::: {#refs}
:::

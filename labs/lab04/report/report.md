---
## Front matter
title: "Лабораторная работа №4"
subtitle: "Задание для самостоятельного выполнения"
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

Выполнить задание для самостоятельного выполнения 

# Задание

1. Для приведённой схемы разработать имитационную модель в пакете NS-2.
2. Построить график изменения размера окна TCP (в Xgraph и в GNUPlot);
3. Построить график изменения длины очереди и средней длины очереди на первом
маршрутизаторе.

**Описание моделируемой сети**:

– сеть состоит из N TCP-источников, N TCP-приёмников, двух маршрутизаторов
R1 и R2 между источниками и приёмниками (N — не менее 20);

– между TCP-источниками и первым маршрутизатором установлены дуплексные
соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью
типа DropTail;

– между TCP-приёмниками и вторым маршрутизатором установлены дуплексные
соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью
типа DropTail;

– между маршрутизаторами установлено симплексное соединение (R1–R2) с про-
пускной способностью 20 Мбит/с и задержкой 15 мс очередью типа RED,
размером буфера 300 пакетов; в обратную сторону — симплексное соедине-
ние (R2–R1) с пропускной способностью 15 Мбит/с и задержкой 20 мс очередью
типа DropTail;

– данные передаются по протоколу FTP поверх TCPReno;

– параметры алгоритма RED: qmin = 75, qmax = 150, qw = 0, 002, pmax = 0.1;

– максимальный размер TCP-окна 32; размер передаваемого пакета 500 байт; время
моделирования — не менее 20 единиц модельного времени

# Выполнение лабораторной работы

1. Создаем файл для разработки описанной в задании имитационной модели (рис. [-@fig:001], [-@fig:002]).

![имитационная модель](image/6.png){#fig:001 width=70%}

![имитационная модель](image/7.png){#fig:002 width=70%}

2. Запускаем скрипт и получаем на выходе схему моделируемой сети (рис. [-@fig:003]) и графики (рис. [-@fig:004], [-@fig:005], [-@fig:006], [-@fig:007])

![схема моделируемой сети ](image/1.png){#fig:003 width=70%}

![график изменения размера окна TCP на всех источниках](image/2.png) {#fig:004 width=70%}

![график изменения размера окна TCP на линке 1 источника](image/3.png){#fig:005 width=70%}

![график изменения размера средней длины очереди](image/4.png){#fig:006 width=70%}

![график изменения размера длины очереди](image/5.png){#fig:007 width=70%}

3. Создаем файл для построения графиков (рис. [-@fig:008], [-@fig:009])

![программа для построения графиков 1/2](image/9.png){#fig:008 width=70%}

![программа для построения графиков 2/2](image/10.png){#fig:009 width=70%}

4. Делаем файл исполняемым и запускаем (рис. [-@fig:008])

![терминал](image/11.png){#fig:011 width=70%}

Получаем следующие графики:


![изменение размера средней длины очереди на линке](image/12.png){#fig:012 width=70%}

![изменение размера длины очереди на линке](image/13.png){#fig:013 width=70%}

![изменение размера окна на линке 1 источника](image/14.png){#fig:014 width=70%}

![изменение размера окна на всех источниках](image/15.png){#fig:015 width=70%}

# Выводы

В результате данной лабораторной работы, было выполнено самостоятельное задание. 

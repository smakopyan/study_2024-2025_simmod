---
## Front matter
title: "Лабораторная работа №5"
subtitle: "Модель эпидемии (SIR)"
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

Целью данной лабораторной работы является реализовать модель SIR

# Теоретическое введение

Модель SIR предложена в 1927 г. (W. O. Kermack, A. G. McKendrick).

Предполагается, что особи популяции размера N могут находиться в трёх различ-
ных состояниях:

– S (susceptible, уязвимые) — здоровые особи, которые находятся в группе риска
и могут подхватить инфекцию;

– I (infective, заражённые, распространяющие заболевание) — заразившиеся пере-
носчики болезни;

– R (recovered/removed, вылечившиеся) — те, кто выздоровел и перестал распро-
странять болезнь (в эту категорию относят, например, приобретших иммунитет
или умерших).

Внутри каждой из выделенных групп особи считаются неразличимыми по свой-
ствам. 

# Выполнение лабораторной работы

1. **Реализация модели в xcos**

В меню Моделирование, Задать переменные окружения зададим значения переменных $β$ и $ν$ (рис. [-@fig:001]).

![Задаем переменные окружения в xcos](image/1.png){#fig:001 width=70%}

Готовая модель SIR представлена на (рис. [-@fig:002])
Первое уравнение модели задано верхним блоком интегрирования, блоком
произведения и блоком задания коэффициента β. Блок произведения соединён с вы-
ходами верхнего и среднего блоков интегрирования и блоком коэффициента β, что
реализует математическую конструкцию s(t)i(t)β.

Третье уравнение модели задано нижним блоком интегрирования и блоком
задания коэффициента ν. Для реализации математической конструкции νi(t) соеди-
няем выход среднего блока интегрирования и вход блока задания коэффициента ν,
а результат передаём на вход нижнего блока интегрирования.
Средний блок интегрирования и блок суммирования определяют второе уравне-
ние модели, которое по сути является суммой правых частей первого и третьего уравнений. Для реализации соединяем входы верхнего и нижнего блоков интегрирования с входами блока суммирования, меняя при этом в его параметрах оба знака на минус. Выход блока суммирования соединяем с входом среднего блока интегрирования.

![Модель SIR](image/7.png){#fig:002 width=70%}

Меняем количество выходов мультиплексора до 3 (рис. [-@fig:003])

![Установить параметры блока мультиплексора](image/3.png){#fig:003 width=70%}

Выходы трёх блоков интегрирования соединяем с мультиплексором.
В параметрах верхнего и среднего блока интегрирования необходимо задать
начальные значения $s(0) = 0$, $0.999$ и $i(0) = 0.001$  (рис. [-@fig:005], [-@fig:006])

![Установить параметры блока сумматора](image/4.png){#fig:004 width=70%}

![Задать начальные значения в блоках интегрирования](image/5.png){#fig:005 width=70%}

![Задать начальные значения в блоках интегрирования](image/6.png){#fig:006 width=70%}


В меню Моделирование, Установка необходимо задать конечное время интегри-
рования, равным времени моделирования (в данном случае 30)

![Задать конечное время интегрирования в xcos](image/8.png){#fig:007 width=70%}

![Эпидемический порог модели SIR](image/10.png){#fig:008 width=70%}

2. **Реализация модели с помощью блока Modelica в xcos**

Готовая модель SIR представлена на (рис. [-@fig:009])

Для реализации модели с помощью языка Modelica помимо блоков CLOCK_c,
CSCOPE, TEXT_f и MUX требуются блоки CONST_m — задаёт константу; MBLOCK
(Modelica generic) — блок реализации кода на языке Modelica. 

![Модель SIR](image/14.png){#fig:009 width=70%}

Параметры блока Modelica представлены на (рис. [-@fig:010], [-@fig:011]). Переменные на входе (“beta”,
“nu”) и выходе (“s”, “i”, “r”) блока заданы как внешние (“E”).

![Параметры блока Modelica для модели SIR](image/11.png){#fig:010 width=70%}

![Параметры блока Modelica для модели SIR](image/13.png){#fig:011 width=70%}

Результат моделирования совпал с результатом при реализации модели с помощью блоков интегрирования

![Эпидемический порог модели SIR](image/10.png){#fig:012 width=70%}


# Выводы

В результате данной лабораторной работы, была реализована модель SIR.
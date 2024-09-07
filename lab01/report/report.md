
## Front matter
title: "Лабораторная работа 1"
author: "Коротун Илья Игоревич"

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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Задание
Создать виртуальную машину для дальнейшего использовния.

#Теоретическое введение

Rocky Linux – это новый дистрибутив Linux от основателя CentOS Грегори Курцера. Полностью бинарно совместим с коммерческим Red Hat Enterprise Linux и призван заместить дистрибутив CentOS.

# Выполнение лабораторной работы

1) Создаю новую виртуальную машину образа Rocky Linux

![к15](image/к15.jpg)

![к1](image/к1.jpg)

2) Задаю параметры для виртуальной машины

![к2](image/к2.jpg)

![к3](image/к3.jpg)

![к4](image/к4.jpg)

![к5](image/к5.jpg)


3) Создаю учетную запись

![к6](image/к6.jpg)

![к7](image/к7.jpg)


4) Запускаю виртуальную машину

![к16](image/к16.jpg)

5) Выполняю домашнее задание

Получите следующую информацию.
1. Версия ядра Linux (Linux version).
2. Частота процессора (Detected Mhz processor).
3. Модель процессора (CPU0).
4. Объем доступной оперативной памяти (Memory available).
5. Тип обнаруженного гипервизора (Hypervisor detected).
6. Тип файловой системы корневого раздела.
7. Последовательность монтирования файловых систем.
   
![к9](image/к9.jpg)

![к10](image/к10.jpg)

![к11](image/к11.jpg)

![к12](image/к12.jpg)

![к13](image/к13.jpg)

![к14](image/к14.jpg)

   
# Выводы
Я приорел навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов

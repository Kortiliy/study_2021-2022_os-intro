![image](https://github.com/Kortiliy/study_2021-2022_os-intro/assets/104276688/7e8195d5-acad-4da3-a10e-6476aab9c165)---
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

Научиться работать с git и выполнить несколько заданий на основе полученных знаний.


# Выполнение лабораторной работы
1) Подготовка (Создание проекта, Внесение изменений, Индексация изменений, Отмена локальных изменений(до индексации), Отмена проиндексированных изменений(перед коммитом)
   Отмена коммитов, Удаление коммиттов из ветки, Удаление тега oops) 
![к1](image/к1.jpg){ #fig:001 width=70% }
![к2](image/к2.jpg){ #fig:001 width=70% }
![к3](image/к3.jpg){ #fig:001 width=70% }
![к4](image/к4.jpg){ #fig:001 width=70% }
![к5](image/к5.jpg){ #fig:001 width=70% }
![к6](image/к6.jpg){ #fig:001 width=70% }
![к7](image/к7.jpg){ #fig:001 width=70% }
![к8](image/к8.jpg){ #fig:001 width=70% }
![к9](image/к9.jpg){ #fig:001 width=70% }
![к10](image/к10.jpg){ #fig:001 width=70% }
![к11](image/к11.jpg){ #fig:001 width=70% }

2) Внесение изменений в коммиты
   
![t1](image/t1.jpg){ #fig:001 width=70% }
![t2](image/t2.jpg){ #fig:001 width=70% }

3) Перемещение файлов
![t3](image/t3.jpg){ #fig:001 width=70% }

4) Подробнее о структуре ( Добавление index.html, Углубляемся в базу данных объектов ).
![t4](image/t4.jpg){ #fig:001 width=70% }
![t5](image/t5.jpg){ #fig:001 width=70% }
# Выводы

Здесь кратко описываются итоги проделанной работы.

# Список литературы{.unnumbered}

::: {#refs}
:::

---
## Front matter
title: "Лабораторная работа №7"
subtitle: " Введение в работу с данными"
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

Основной целью работы является использование специализированных пакетов Julia для обработки данных.


# Задание

1. Используя Jupyter Lab, повторите примеры из раздела 7.2.
2. Выполните задания для самостоятельной работы (раздел 7.4).

# Теоретическое введение

Обработка и анализ данных, полученных в результате проведения исследований, — важная и неотъемлемая часть исследовательской деятельности. Большое значение имеет выявление определённых связей и закономерностей в имеющихся неструктурированных данных, особенно в данных больших размерностей. Выявленные в данных связей и закономерностей позволяет строить прогнозные модели с предполагаемым результатом. Для решения таких задач применяют методы из таких областей знаний как математическая статистика, программирование, искусственный интеллект, машинное обучение.


# Выполнение лабораторной работы

## Повторил примеры из методички

## Julia для науки о данных

# 1. Считывание данных

![Рисунок1](image/r1.jpg)

![Рисунок2](image/r2.jpg)

![Рисунок3](image/r3.jpg)


# 2. Запись данных в файл

![Рисунок4](image/r4.jpg)


# 3. Словари

![Рисунок5](image/r5.jpg)

![Рисунок6](image/r6.jpg)


# 4. RDatasets

![Рисунок7](image/r7.jpg)


# 5. Работа с переменными отсутствующего типа (Missing Values)

![Рисунок8](image/r8.jpg)

![Рисунок9](image/r9.jpg)


# 6. FileIO

![Рисунок10](image/r10.jpg)


## Обработка данных: стандартные алгоритмы машинного обучения в Julia

# Кластеризация данных. Метод k-средних

![Рисунок11](image/r11.jpg)

![Рисунок12](image/r12.jpg)

![Рисунок13](image/r13.jpg)

![Рисунок14](image/r14.jpg)

![Рисунок15](image/r15.jpg)

![Рисунок16](image/r16.jpg)

![Рисунок17](image/r17.jpg)


# Кластеризация данных. Метод k ближайших соседей

![Рисунок18](image/r18.jpg)

![Рисунок19](image/r19.jpg)


# Обработка данных. Метод главных компонентов

![Рисунок20](image/r20.jpg)

![Рисунок21](image/r21.jpg)

![Рисунок22](image/r22.jpg)


# Обработка данных. Линейная регрессия

![Рисунок23](image/r23.jpg)

![Рисунок24](image/r24.jpg)

![Рисунок25](image/r25.jpg)

![Рисунок26](image/r26.jpg)

![Рисунок27](image/r27.jpg)

## Задания для самостоятельного выполнения

![Рисунок28](image/r28.jpg)

![Рисунок29](image/r29.jpg)


# Кластеризация

![Рисунок30](image/r30.jpg)

![Рисунок31](image/r31.jpg)


#  Регрессия (метод наименьших квадратов в случае линейной регрессии)

# Часть 1

![Рисунок32](image/r32.jpg)

![Рисунок33](image/r33.jpg)


# Часть 2

![Рисунок34](image/r34.jpg)

![Рисунок35](image/r35.jpg)


# Модель ценообразования биномиальных опционов

![Рисунок36](image/r36.jpg)

![Рисунок37](image/r37.jpg)

![Рисунок38](image/r38.jpg)

![Рисунок39](image/r39.jpg)


# Выводы

Я освоил специализированные пакеты Julia для обработки данных и выполнил задания, поставленные в Лабораторной работе 7.


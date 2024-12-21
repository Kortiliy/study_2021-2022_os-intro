![image](https://github.com/user-attachments/assets/f6dba59d-c1ec-48e0-8b06-9fd58f5fcf04)---
## Front matter
title: "Лабораторная работа №6"
subtitle: "Решение моделей в непрерывном и дискретном времени"
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

# Цель работы.

Основной целью работы является освоение специализированных пакетов для решения задач в непрерывном и дискретном времени.

# Задание

1. Используя Jupyter Lab, повторите примеры из раздела 6.2.
2. Выполните задания для самостоятельной работы (раздел 6.4).


# Теоретическое введение

Решение обыкновенных дифференциальных уравнений
Напомним, что обыкновенное дифференциальное уравнение (ОДУ) описывает изменение некоторой переменной 𝑢:
𝑢′(𝑡) = 𝑓(𝑢(𝑡), 𝑝, 𝑡),
где 𝑓(𝑢(𝑡), 𝑝, 𝑡) — нелинейная модель (функция) изменения 𝑢(𝑡) с заданным начальным
значением 𝑢(𝑡0) = 𝑢0, 𝑝 — параметры модели,𝑡 — время.
Для решения обыкновенных дифференциальных уравнений (ОДУ) в Julia можно использовать пакет diffrentialEquations.jl.


# Выполнение лабораторной работы

Повторил примеры из методички

1. Модель экспоненциального роста

![Рисунок1](image/е1.jpg)

![Рисунок2](image/е2.jpg)

![Рисунок3](image/е3.jpg)

![Рисунок4](image/е4.jpg)


2.  Система Лоренца

![Рисунок5](image/е5.jpg)

![Рисунок6](image/е6.jpg)


3. Модель Лотки–Вольтерры

![Рисунок7](image/е7.jpg)

![Рисунок8](image/е8.jpg)

![Рисунок9](image/е9.jpg)


# Задания для самостоятельного выполнения

![Рисунок10](image/е10.jpg)

![Рисунок11](image/е11.jpg)

## №1 Модель Мальтуса

![Рисунок12](image/е12.jpg)

![Рисунок13](image/е13.jpg)


## №2 Модель роста популяции

![Рисунок14](image/е14.jpg)

![Рисунок15](image/е15.jpg)


## №3 Модель эпидемии Кермака–Маккендрика (SIR модель)

![Рисунок16](image/е16.jpg)

![Рисунок17](image/е17.jpg)


## №4 SEIR Модель

![Рисунок18](image/е18.jpg)

![Рисунок19](image/е19.jpg)


## №5 Дискретная модель Лотки–Вольтерры

![Рисунок20](image/е20.jpg)

![Рисунок21](image/е21.jpg)

## Аналитичнское решение и фазовый портрет

![Рисунок22](image/е22.jpg)

![Рисунок23](image/е23.jpg)


## №6 Модель отбора на основе конкурентных отношений

![Рисунок24](image/е24.jpg)

![Рисунок25](image/е25.jpg)

## Фазовый портрет

![Рисунок26](image/е26.jpg)


## №7 Модель консервативного гармонического осциллятора

![Рисунок27](image/е27.jpg)

![Рисунок28](image/е28.jpg)

## Фазовый портрет

![Рисунок29](image/е29.jpg)


## №8 Модель свободных колебаний гармонического осциллятора

![Рисунок30](image/е30.jpg)

![Рисунок31](image/е31.jpg)

## Фазовый портрет

![Рисунок32](image/е32.jpg)


# Выводы

Я освоил специализированные пакеты для решения задач в непрерывном и дискретном времени. С помощью полученных навыков выполнил Лабораторную работу №6.


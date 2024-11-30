---
## Front matter
title: "Лабораторная работа 3"
subtitle: "Markdown"
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

Цель: Основная цель работы — освоить применение циклов функций и сторонних для Julia пакетов для решения задач линейной алгебры и работы с матрицами.

# Задание

1. Используя Jupyter Lab, повторите примеры из раздела 3.2.
2. Выполните задания для самостоятельной работы (раздел 3.4).

# Теоретическое введение

Для различных операций, связанных с перебором индексируемых элементов структур данных, традиционно используются циклы while и for.

Синтаксис while
while <условие>
  <тело цикла>
end

Довольно часто при решении задач требуется проверить выполнение тех или иных условий. Для этого используют условные выражения.
Синтаксис условных выражений с ключевым словом:
if <условие 1>
  <действие 1>
elseif <условие 2>
  <действие 2>
else
  <действие 3>
end

Julia дает нам несколько разных способов написать функцию. Первый требует ключевых слов function и end:
function sayhi(name)
  println("Hi $name, it's great to see you!")
end

Вызов функции осуществляется по её имени с указанием аргументов, например:
sayhi("C-3PO")

По соглашению в Julia функции, сопровождаемые восклицательным знаком, изменяют свое содержимое, а функции без восклицательного знака не делают этого.

Функция sort(v) возвращает отсортированный массив, который содержит те же
элементы, что и массив v, но исходный массив v остаётся без изменений. Если же использовать sort!(v), то отсортировано будет содержимое исходного массива v.
В программировании под функцией высшего порядка понимается функция, принимающая в качестве аргументов другие функции или возвращающая другую функцию в качестве результата. Основная идея состоит в том, что функции имеют тот же статус, что и другие объекты данных. В Julia функция map является функцией высшего порядка, которая принимает функцию в качестве одного из своих входных аргументов и применяет эту функцию к каждому элементу структуры данных, которая ей передаётся также в качестве аргумента.


# Выполнение лабораторной работы

1. Осваиваем новый материал, повторяя примеры из методички.

1.1. Циклы while и for

![Рисунок1](image/j4.jpg)

![Рисунок2](image/j5.jpg)

![Рисунок3](image/j6.jpg)

1.2. Условные выражения

![Рисунок4](image/j7.jpg)

1.3. Функции

![Рисунок5](image/j8.jpg)

![Рисунок6](image/j9.jpg)

![Рисунок7](image/j10.jpg)

1.4. Сторонние библиотеки (пакеты) в Julia

![Рисунок8](image/j11.jpg)

![Рисунок9](image/j12.jpg)


# Задания для самостоятельного выполнения

![Рисунок10](image/j1.jpg)

![Рисунок11](image/j2.jpg)

![Рисунок12](image/j3.jpg)

Задание 1

![Рисунок13](image/j13.jpg)

![Рисунок14](image/j14.jpg)

Задание 2

![Рисунок15](image/j15.jpg)

Задание 3

![Рисунок16](image/j16.jpg)

Задание 4

![Рисунок17](image/j17.jpg)

Задание 5

![Рисунок18](image/j18.jpg)

Задание 6

![Рисунок19](image/j19.jpg)

Задание 7

![Рисунок20](image/j20.jpg)

![Рисунок21](image/j21.jpg)

![Рисунок22](image/j22.jpg)

Задание 8

![Рисунок23](image/j23.jpg)

Задание 9

![Рисунок24](image/j24.jpg)

Задание 10

![Рисунок25](image/j25.jpg)

![Рисунок26](image/j26.jpg)

![Рисунок27](image/j27.jpg)

Задание 11

![Рисунок28](image/j28.jpg)

# Выводы

Я освоил применение циклов функций и сторонних для Julia пакетов для решения задач линейной алгебры и работы с матрицами. С помощью полученных навыков выполнил Лабораторную работу №3. 

# Список литературы

...

---
## Front matter
lang: ru-RU
title: Structural approach to the deep learning method
author: |
	Leonid A. Sevastianov\inst{1,3}
	\and
	Anton L. Sevastianov\inst{1}
	\and
	Edik A. Ayrjan\inst{2}
	\and
	Anna V. Korolkova\inst{1}
	\and
	Dmitry S. Kulyabov\inst{1,2}
	\and
	Imrikh Pokorny\inst{4}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
	\and
	\inst{2}LIT JINR, Dubna, Russian Federation
	\and
	\inst{3}BLTP JINR, Dubna, Russian Federation
	\and
	\inst{4}Technical University of Košice, Košice, Slovakia
date: NEC--2019, 30 September -- 4 October, 2019 Budva, Montenegro

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Лабораторная работа №13

## Средства, применяемые при разработке программного обеспечения в ОС типа UNIX/Linux


## Цель работы

Приобрести простейшие навыки разработки, анализа, тестирования и отладки приложений в ОС типа UNIX/Linux на примере создания на языке программирования С калькулятора с простейшими функциями.

## Выполнение лабораторной работы

## 1 ШАГ. Ознакомился с теоретическим материалом

## 2 ШАГ. В домашнем каталоге создал подкаталог ~/work/os/lab_prog

![Рисунок1](image/я1.JPG)

## 3 ШАГ. Создал в нём файлы: calculate.h, calculate.c, main.c

![Рисунок2](image/я2.JPG)

## 4 ШАГ. Написал команды в файлы

![Рисунок3](image/я3.JPG)

![Рисунок4](image/я4.JPG)

![Рисунок5](image/я5.JPG)


## 5 ШАГ. Выполнил компиляцию программы посредством gcc

![Рисунок6](image/я6.JPG)

## 6 ШАГ. Проверил работу на синтаксические ошибки

## 7 ШАГ. Создал Makefile со следующим содержанием

![Рисунок7](image/я7.JPG)

## 8 ШАГ. С помощью gdb выполнил отладку программы calcul.

![Рисунок8](image/я8.JPG)

## 9 ШАГ. С помощью утилиты splint попробовал проанализировать коды файлов calculate.c и main.c

![Рисунок9](image/я9.JPG)

## Выводы

Я приобрёл простейшие навыки разработки, анализа, тестирования и отладки приложений в ОС типа UNIX/Linux на примере создания на языке программирования С калькулятора с простейшими функциями.

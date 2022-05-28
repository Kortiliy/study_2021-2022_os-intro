
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

# Лабораторная работа №11

## Программирование в командном процессоре ОС UNIX. Ветвления и циклы

## Цель работы

Изучить основы программирования в оболочке ОС UNIX. Научится писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.

## Выполнение лабораторной работы

## 1 ШАГ. Используя команды getopts grep, написал командный файл, который анализирует командную строку с ключами:

– -i inputfile — прочитать данные из указанного файла;

– -o outputfile — вывести данные в указанный файл;

– -p шаблон — указать шаблон для поиска;

– -C — различать большие и малые буквы;

– -n — выдавать номера строк.

а затем ищет в указанном файле нужные строки, определяемые ключом -p.


1.1 Написал командный файл

![Рисунок1](image/я1.JPG)

1.2 Заполнил inputfile.txt различными словами

![Рисунок2](image/я2.JPG)

1.3 Проверил работу

![Рисунок3](image/я3.JPG)

## 2 ШАГ. Написал на языке Си программу, которая вводит число и определяет, является ли оно больше нуля, меньше нуля или равно нулю.

2.1 Написал программу на языке Си

![Рисунок4](image/я4.JPG)

2.2 Написал командный файл

![Рисунок5](image/я5.JPG)

2.3 Проверил работу

![Рисунок6](image/я6.JPG)

## 3 ШАГ. Написал командный файл, создающий указанное число файлов, пронумерованных последовательно от 1 до 𝑁 (например 1.tmp, 2.tmp, 3.tmp,4.tmp и т.д.).

3.1 Написал командный файл

![Рисунок7](image/я7.JPG)

3.2 Проверил работу

![Рисунок8](image/я8.JPG)

## 4 ШАГ. Написал командный файл, который с помощью команды tar запаковывает в архив все файлы в указанной директории. Модифицировал его так, чтобы запаковывались только те файлы, которые были изменены менее недели тому назад (используя команду find).

3.1 Написал командный файл

![Рисунок9](image/я9.JPG)

3.2 Проверил работу

![Рисунок10](image/я10.JPG)

## Выводы

Я изучил основы программирования в оболочке ОС UNIX. Научился писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.

## Ответил на все контрольные вопросы

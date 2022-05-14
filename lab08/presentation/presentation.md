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

# Лабораторная работа №8

## Текстовой редактор vi

## Цель работы

Познакомиться с операционной системой Linux. Получить практические навыки работы с редактором vi, установленным по умолчанию практически во всех дистрибутивах.

## Выполнение лабораторной работы

## 1 ШАГ. Ознакомился с теоретическим материалом. Ознакомился с редактором vi.



## 2 ШАГ. Начал выполнение Задания 1. Создал каталог с именем ~/work/os/lab06 и перешел во вновь созданный каталог.

![Рисунок1](image/я1.JPG)

## 3 ШАГ. Вызвал vi и создал файл hello.sh

![Рисунок2](image/я2.JPG)

## 4 ШАГ. Нажал клавишу i и ввел следующий текст

![Рисунок3](image/я3.JPG)

## 5 ШАГ. Нажал клавишу Esc для перехода в командный режим после завершения ввода текста. Нажал : для перехода в режим последней строки. Нажал w (записать) и q (выйти), а затем нажал клавишу Enter для сохранения текста и завершения работы.

![Рисунок4](image/я4.JPG)

## 6 ШАГ. Сделал файл исполняемым

![Рисунок5](image/я5.JPG)

## 7 ШАГ. Начал выполнение Задания 2. Вызвал vi на редактирование файла

![Рисунок6](image/я6.JPG)

## 8 ШАГ. Установил курсор в конец слова HELL второй строки. Перешел в режим вставки и заменил на HELLO. Нажал Esc для возврата в командный режим.

![Рисунок7](image/я7.JPG)

## 9 ШАГ. Установил курсор на четвертую строку и стер слово LOCAL. Перешел в режим вставки и набрал следующий текст: local, нажал Esc для возврата в командный режим.

![Рисунок8](image/я8.JPG)

## 10 ШАГ. Установил курсор на последней строке файла. Вставил после неё строку, содержащую следующий текст: echo $HELLO. Нажал Esc для перехода в командный режим. Удалил последнюю строку. Ввел команду отмены изменений u для отмены последней команды. Ввел символ : для перехода в режим последней строки. Записал произведённые изменения и вышел из vi.

![Рисунок9](image/я9.JPG)

## 11 ШАГ. Проверил работу файла

![Рисунок10](image/я10.JPG)

## Выводы
Я познакомился с операционной системой Linux. Получил практические навыки работы с редактором vi.

## Ответил на все контрольные вопросы

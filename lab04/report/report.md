![image](https://github.com/user-attachments/assets/34af37d7-1b81-4827-8e50-3380a062caea)---
## Front matter
title: "Лабораторная работа №4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
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
Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Задание
Выполнить несколько пунктов согласно методичке.

# Теоретическое введение

Дискреционное управление доступом
Права доступа состоят из трех компонентов: владелец файла, группа владельца и остальные пользователи. Каждому компоненту присваивается разрешение на чтение (r), запись (w) и выполнение (x). Для управления правами доступа в Linux используются команды chmod, chown и chgrp.


# Выполнение лабораторной работы

1. От имени пользователя guest определил расширенные атрибуты файла /home/guest/dir1/file1 командой
lsattr /home/guest/dir1/file1

![j1](image/j1.jpg)

2. Установил командой chmod 600 file1 на файл file1 права, разрешающие чтение и запись для владельца файла.

3. Попробовал установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest:
chattr +a /home/guest/dir1/file1

В ответ получил отказ от выполнения операции

![j2](image/j2.jpg)

4. Зашел на третью консоль с правами администратора и попробовал установить расширенный атрибут a на файл /home/guest/dir1/file1 от имени суперпользователя:
chattr +a /home/guest/dir1/file1

![j3](image/j3.jpg)

5. От пользователя guest проверил правильность установления атрибута:
lsattr /home/guest/dir1/file1

![j4](image/j4.jpg)

6. Выполнил дозапись в файл file1 слова «test» командой
echo "test" /home/guest/dir1/file1

После этого выполните чтение файла file1 командой
cat /home/guest/dir1/file1

![j5](image/j5.jpg)

7. Попробовал удалить файл file1 либо стереть имеющуюся в нём информацию командой
echo "abcd" > /home/guest/dirl/file1

Попробовал переименовать файл командой mv 

Получил отказ.

8. Попробовал с помощью команды chmod 000 file1 установить на файл file1 права, например, запрещающие чтение и запись для владельца файла.
Получил октаз.

9. Снял расширенный атрибут a с файла /home/guest/dirl/file1 от имени суперпользователя командой
chattr -a /home/guest/dir1/file1

![j6](image/j6.jpg)

Повторил операции, которые мне ранее не удавалось выполнить. В этот раз получилось установить на файл права.

10. Повторил все действия по шагам, заменив атрибут «a» атрибутом «i».
Из изменений получил отказ используя команду cat

![j7](image/j6.jpg)

![j8](image/j6.jpg)


# Выводы

Я получил практические навыки работы в консоли с расширенными атрибутами файлов.

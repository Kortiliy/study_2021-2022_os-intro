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


# Лабораторная работа 4

## Коротун Илья Игоревич
## НКНбд-01-21
## Москва 2024г.

# Цели

Цель: ознакомится с материалом по моделям гармонических колебаний и на основе полученных знаний выполнить Лабораторную работу №4.


# Задание

Вариант № 29

Постройте фазовый портрет гармонического осциллятора и решение уравнения гармонического осциллятора для следующих случаев

1. Колебания гармонического осциллятора без затуханий и без действий внешней силы

![Рисунок1](image/g1.jpg){ #случай 1 }
   
2. Колебания гармонического осциллятора c затуханием и без действий внешней силы
   
![Рисунок2](image/g2.jpg){ #случай 2 }
   
3. Колебания гармонического осциллятора c затуханием и под действием внешней силы

![Рисунок3](image/g3.jpg){ #случай 3 }

На интервале t [0;38] (шаг 0.05) с начальными условиями x0 = 0.9, y0 = -1.9

# Ход работы 

## Julia: 

## Для начала введем необходимые библиотеки

using DifferentialEquations

using Plots

## Зададим начальные данные 

p1 = [0, 5.1]

p2 = [0.9, 2.0]

p3 = [0.9, 1.9]

tspan = (0,38)

x0 = [-1.9, 0.9]

## Также зададим значение внешних сил

f(t) = 3.3*cos(5*t)

## Затем введем 2 функции. Первая для колебания без действия внешних сил, а вторая с этим действием.

function funk(dx,x,p,t)

    gamma, w = p
    
    dx[1] = x[2]
    
    dx[2] = -w .* x[1] - gamma .* x[2]
    
end


function funk2(dx,x,p,t)

    gamma, w = p
    
    dx[1] = x[2]
    
    dx[2] = -w .* x[1] - gamma .* x[2] .+ f(t)
    
end


## Затем распишем решение и вывод графиков для трех случаев

problem1 = ODEProblem(funk, x0, tspan, p1)

solution = solve(problem1, dtmax = 0.05)


problem2 = ODEProblem(funk, x0, tspan, p2)

solution2 = solve(problem2, dtmax = 0.05)


problem3 = ODEProblem(funk2, x0, tspan, p3)

solution3 = solve(problem3, dtmax = 0.05)


plot(solution)


![Рисунок5](image/н1.jpg){ # Колебания гармонического осциллятора случай 1 }

plot(solution, vars = (2,1))

![Рисунок6](image/н2.jpg){ #  Фазовый портрет случай 1 }

plot(solution2)

![Рисунок7](image/н3.jpg){ # Колебания гармонического осциллятора случай 2 }

plot(solution2, vars = (2,1))

![Рисунок8](image/н4.jpg){ # Фазовый портрет случай 2 }

plot(solution3)

![Рисуно9](image/н5.jpg){ # Колебания гармонического осциллятора случай 3 }

plot(solution3, vars = (2,1))

![Рисунок10](image/н6.jpg){ # Фазовый портрет случай 3 }


## Теперь построим такой же график в OpenModelica


![Рисунок11](image/н9.jpg){ # Случай 1 }

## Результат

![Рисунок12](image/н8.jpg){ # Колебания гармонического осциллятора случай 1 }


![Рисунок17](image/н14.jpg){ # Фазовый портрет случай 1 }




![Рисунок13](image/н16.jpg){ # Случай 2 }

## Результат

![Рисунок14](image/н10.jpg){ # Колебания гармонического осциллятора случай 2 }


![Рисунок18](image/н15.jpg){ # Фазовый портрет случай 2 }



![Рисунок15](image/н13.jpg){ # Случай 3 }

## Результат

![Рисунок16](image/н11.jpg){ # Колебания гармонического осциллятора случай 3 }


![Рисунок19](image/н12.jpg){ # Фазовый портрет случай 3 }


# Выводы

Я ознакомитлся с материалом и на основе полученных знаний выполнил Лабораторную работу №4 (Построение фазового портрета гармонического осциллятора и решение уравнения гармонического осциллятора).
 


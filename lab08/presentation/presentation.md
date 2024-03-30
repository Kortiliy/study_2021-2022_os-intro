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

# Лабораторная работа 8

## Коротун Илья Игоревич

## НКНбд-01-21

## Москва 2024г.

# Цели

Ознакомится с материалом и на основе полученных знаний выполнить Лабораторную работу №8 в которой необходимо было построить модели конкурирующих фирм. 

# Задание

Вариант 29

Случай 1. Рассмотрим две фирмы, производящие взаимозаменяемые товары одинакового качества и находящиеся в одной рыночной нише. Считаем, что в рамках
нашей модели конкурентная борьба ведётся только рыночными методами. То есть, конкуренты могут влиять на противника путем изменения параметров своего
производства: себестоимость, время цикла, но не могут прямо вмешиваться в ситуацию на рынке («назначать» цену или влиять на потребителей каким-либо иным
способом.) Будем считать, что постоянные издержки пренебрежимо малы, и в модели учитывать не будем. В этом случае динамика изменения объемов продаж
фирмы 1 и фирмы 2 описывается следующей системой уравнений:

![Рисунок1](image/b5.jpg){условие 1}


Случай 2. Рассмотрим модель, когда, помимо экономического фактора влияния (изменение себестоимости, производственного цикла, использование
кредита и т.п.), используются еще и социально-психологические факторы – формирование общественного предпочтения одного товара другому, не зависимо от
их качества и цены. В этом случае взаимодействие двух фирм будет зависеть друг от друга, соответственно коэффициент перед M1 M2 будет отличаться. Пусть в
рамках рассматриваемой модели динамика изменения объемов продаж фирмы 1 и фирмы 2 описывается следующей системой уравнений:

![Рисунок2](image/b6.jpg){условие 2}


Для обоих случаев рассмотрим задачу со следующими начальными условиями и параметрами:

![Рисунок3](image/b7.jpg){условие 2}


# Ход работы 

## Julia:

## Для начала введем необходимые библиотеки

using DifferentialEquations
using Plots

## Зададим параметры

M10 = 8.5
M20 = 9.1
Pcr = 33
N = 83
q = 1
t1 = 27
t2 = 24
p1 = 11.3
p2 = 12.5

## Зададим функции

function funk1(du ,u ,p ,t )

    a1, a2, b, c1, c2 = p
    du[1] = u[1] - b/c1 * u[1] * u[2] - a1/c1 * u[1]^2
    du[2] = c2/c1 * u[2] - b/c1 * u[1]*u[2] - a2/c1 * u[2]^2
    
end

function funk2(du ,u ,p ,t )

    a1, a2, b, c1, c2 = p
    du[1] = u[1] - (b/c1 +0.00019) * u[1] * u[2] - a1/c1 * u[1]^2
    du[2] = c2/c1 * u[2] - b/c1 * u[1]*u[2] - a2/c1 * u[2]^2
    
end

a1 = Pcr/(t1^2 * p1^2 * N * q)
a2 = Pcr/(t2^2 * p2^2 * N * q)
b = Pcr/(t1^2 * p1^2 * t2^2 * p2^2 * N * q)
c1 = (Pcr - p1)/(t1 * p1)
c2 = (Pcr - p2)/(t2 * p2)

p = [a1, a2, b ,c1 ,c2]
tspan = (0, 20)


## Распишем решение и ввод графиков

problem1 = ODEProblem(funk1, [M10, M20], tspan, p)
solution1 = solve(problem1, Tsit5(), dtmax = 0.05)

problem2 = ODEProblem(funk2, [M10, M20], tspan, p)
solution2 = solve(problem2, Tsit5(), dtmax = 0.05)


plot(solution1)
plot(solution2)


## Результат случай 1

![Рисунок5](image/b1.jpg){случай 1}

## Результат случай 2

![Рисунок6](image/b2.jpg){случай 2}

## Теперь построим такой же график в OpenModelica

## 1 случай 

model lab8


parameter Real Pcr = 33;

parameter Real N = 83;

parameter Real q = 1;

parameter Real t1 = 27;

parameter Real t2 = 24;

parameter Real p1 = 11.3;

parameter Real p2 = 12.5;


parameter Real a1 = Pcr/(t1^2 * p1^2 * N * q);

parameter Real a2 = Pcr/(t2^2 * p2^2 * N * q);

parameter Real b = Pcr/(t1^2 * p1^2 * t2^2 * p2^2 * N * q);

parameter Real c1 = (Pcr - p1)/(t1 * p1);

parameter Real c2 = (Pcr - p2)/(t2 * p2);



Real M10(start = 8.5);

Real M20(start = 9.1);


equation


 der(M10) = M10 - b/c1 * M10 * M20 - a1/c1 * M10^2;
 
 der(M20) = c2/c1 * M20 - b/c1 * M10 * M20 - a2/c1 * M20^2;
 

end lab8;


![Рисунок7](image/b3.jpg){случай 1}


## 2 случай 

model lab8


parameter Real Pcr = 33;

parameter Real N = 83;

parameter Real q = 1;

parameter Real t1 = 27;

parameter Real t2 = 24;

parameter Real p1 = 11.3;

parameter Real p2 = 12.5;


parameter Real a1 = Pcr/(t1^2 * p1^2 * N * q);

parameter Real a2 = Pcr/(t2^2 * p2^2 * N * q);

parameter Real b = Pcr/(t1^2 * p1^2 * t2^2 * p2^2 * N * q);

parameter Real c1 = (Pcr - p1)/(t1 * p1);

parameter Real c2 = (Pcr - p2)/(t2 * p2);


Real M10(start = 8.5);

Real M20(start = 9.1);


equation


 der(M10) = M10 - (b/c1 + 0.00019) * M10 * M20 - a1/c1 * M10^2;
 
 der(M20) = c2/c1 * M20 - b/c1 * M10 * M20 - a2/c1 * M20^2;
 

end lab8;


![Рисунок8](image/b4.jpg){случай 2}


# Выводы

Я ознакомился с материалом и на основе полученных знаний выполнил Лабораторную работу №8 в которой необходимо было построить модели конкурирующих фирм. 

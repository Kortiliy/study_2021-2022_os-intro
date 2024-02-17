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

# Лабораторная работа №2
# Задача о погоне

## Цель
Ознакомится с материалом и на основе полученных знаний выполнить лабораторную работу №2, которая включает в себя задачу о погоне. Выполнить ее с помощью кода, написанного на языке Julia.

## Задание

Вариант 29

На море в тумане катер береговой охраны преследует лодку браконьеров.
Через определенный промежуток времени туман рассеивается, и лодка
обнаруживается на расстоянии 11,8 км от катера. Затем лодка снова скрывается в
тумане и уходит прямолинейно в неизвестном направлении. Известно, что скорость
катера в 4,2 раза больше скорости браконьерской лодки.

1. Запишите уравнение, описывающее движение катера, с начальными
условиями для двух случаев (в зависимости от расположения катера
относительно лодки в начальный момент времени).

3. Постройте траекторию движения катера и лодки для двух случаев.
   
4. Найдите точку пересечения траектории катера и лодки



## Выполнение лабораторной работы

Чтобы найти расстояние x (расстояние после которого катер начнет двигаться вокруг полюса), необходимо составить простое уравнение: 
Случай первый: 

![k1](image/k1.jpg.png)


Случай второй: 

![k3](image/k3.jpg.png)


Отсюда мы найдем два значения

X1

![k2](image/k2.JPG.png)

X2

![k4](image/k4.jpg.png)

После того, как катер береговой охраны окажется на одном расстоянии от полюса, что и лодка, он должен сменить прямолинейную траекторию и начать двигаться вокруг полюса удаляясь от него со скоростью лодки v.
Для этого скорость катера раскладываем на две составляющие: Vr - радиальная скорость и Vt - тангенциальная скорость. Радиальная скорость - это скорость, с которой катер удаляется от полюса ![k5](image/k5.jpg.png),
Нам нужно, чтобы эта скорость была равна скорости лодки, поэтому полагаем ![k6](image/k6.jpg.png).
Тангенциальная скорость – это линейная скорость вращения катера относительно полюса. Она равна произведению угловой скорости ![k7](image/k7.jpg.png) на радиус ![k8](image/k8.jpg.png)

![k9](image/k9.jpg.png)

Решение исходной задачи сводится к решению системы из двух дифференциальных уравнений:

![k10](image/k10.jpg.png)


Точки пересечения.
Угол передвижения - 3pi/4
Для первого случая берем угол - 7pi/4, для второго -pi/4.

![k11](image/k11.jpg.png)

## Код работы

using Plots 
using OrdinaryDiffEq 
s = 11.8 
fi = 3*pi/4

sl_1 = s/5.2 
sl_2 = s/3.2 

tetha1 = (0.0,2*pi)
tetha2 = (-pi,pi)

f(u,p,t) = u/sqrt(16.64) 
f2(t) = tan(fi)*t  

resh1=ODEProblem(f, sl_1, tetha1)
sol1 = solve(resh1, Tsit5(), saveat=0.01) 

resh2=ODEProblem(f, sl_2, tetha2)
sol2 = solve(resh2, Tsit5(), saveat=0.01) 

t = 0:0.01:15
solution1(t) = (sl_1)*exp(1/sqrt(16.64)*t) 
intersection_r1 = solution1(7*pi/4) 

plot!(fill(fi,length(t)), f2.(t))

plot(sol1.t, sol1.u,
proj=:polar,
lims=(0,13)
)

solution2(t) = (sl_2)*exp(5*pi*sqrt(299)/299)*exp(1/sqrt(16.4)*t) 
intersection_r2 = solution2(-pi/4)

plot!(fill(fi,length(t)), f2.(t))

plot(sol2.t, sol2.u,
proj=:polar,
lims=(0,13)
)

## Результат работы

![k12](image/k12.jpg.jpg)


![k13](image/k13.jpg.jpg)


Точка пересечения при 1 случае - 8.733767756285518

Точка пересечения при 2 случае - 7.533979887816658

## Выводы

Я ознакомился с материалом и на основе полученных знаний выполнил лабораторную работу №2, которая включает в себя задачу о погоне. Выполнил ее с помощью кода, написанного на языке Julia.

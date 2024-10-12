---
## Front matter
title: "Лабораторная работа №6"
subtitle: "Мандатное разграничение прав в Linux"
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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux1. Проверить работу SELinx на практике совместно с веб-сервером Apache.


# Задание

Выполнить все пункты согласно методичке.

# Теоретическое введение

SELinux (SELinux) — это система принудительного контроля доступа, реализованная на уровне ядра. Впервые эта система появилась в четвертой версии CentOS, а в 5 и 6 версии реализация была существенно дополнена и улучшена. Эти улучшения позволили SELinux стать универсальной системой, способной эффективно решать массу актуальных задач. Стоит помнить, что классическая система прав Unix применяется первой, и управление перейдет к SELinux только в том случае, если эта первичная проверка будет успешно пройдена.

# Выполнение лабораторной работы

1. Вошел в систему с полученными учётными данными и убедился, что SELinux работает в режиме enforcing политики targeted с помощью команд getenforce и sestatus.

![Рисунок1](image/k1.jpg)

2. Обратился с помощью браузера к веб-серверу, запущенному на моем компьютере, и убедился, что последний работает:
service httpd status или /etc/rc.d/init.d/httpd status

![Рисунок2](image/k2.jpg)

![Рисунок3](image/k3.jpg)

3. Нашел веб-сервер Apache в списке процессов, определил его контекст безопасности. Команды ps auxZ | grep httpd или ps -eZ | grep httpd

![Рисунок4](image/k4.jpg)

4. Посмотрел текущее состояние переключателей SELinux для Apache с помощью команды sestatus -bigrep httpd

![Рисунок5](image/k5.jpg)

5. Посмотрел статистику по политике с помощью команды seinfo, также определил множество пользователей, ролей, типов.

![Рисунок6](image/k6.jpg)

6. Определил тип файлов и поддиректорий, находящихся в директории /var/www, с помощью команды ls -lZ /var/www

![Рисунок7](image/k7.jpg)

7. Определил тип файлов, находящихся в директории /var/www/html: ls -lZ /var/www/html

![Рисунок8](image/k8.jpg)

8. Определил круг пользователей, которым разрешено создание файлов вдиректории /var/www/html.

9. Создайте от имени суперпользователя (так как в дистрибутиве после установки только ему разрешена запись в директорию) html-файл /var/www/html/test.html следующего содержания:
    
<html>
<body>test</body>
</html>

10. Проверил контекст созданного файла.

![Рисунок9](image/k9.jpg)

11. Обратился к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html.

![Рисунок10](image/k10.jpg)

12. Изучил справку man httpd_selinux и выяснил, какие контексты файлов определены для httpd. Проверил контекст файла ls -Z /var/www/html/test.html

![Рисунок11](image/k11.jpg)

13. Изменил контекст файла /var/www/html/test.html с httpd_sys_content_t на любой другой, к которому процесс httpd не имеет доступа, например, на samba_share_t:
chcon -t samba_share_t /var/www/html/test.htm

14. Попробовал ещё раз получить доступ к файлу через веб-сервер, введя в
браузере адрес http://127.0.0.1/test.html. Получил сообщение об ошибке:
Forbidden
You don't have permission to access /test.html on this server.

![Рисунок12](image/k12.jpg)

15. Проанализировал ситуацию.
ls -l /var/www/html/test.html

Просмотрел log-файлы веб-сервера Apache. Также просмотрел системный лог-файл:
tail /var/log/messages

![Рисунок13](image/k13.jpg)

16. Попробовал запустить веб-сервер Apache на прослушивание ТСР-порта
81 (а не 80, как рекомендует IANA и прописано в /etc/services). Для
этого в файле /etc/httpd/httpd.conf нашел строчку Listen 80 и
заменил её на Listen 81.

![Рисунок14](image/k14.jpg)

17. Выполнил перезапуск веб-сервера Apache. Произошёл сбой.

![Рисунок15](image/k15.jpg)

18. Проанализировал лог-файлы:
tail -nl /var/log/messages
Просмотрите файлы /var/log/http/error_log,
/var/log/http/access_log и /var/log/audit/audit.log и
выясните, в каких файлах появились записи.

![Рисунок16](image/k16.jpg)

19. Выполнил команду
semanage port -a -t http_port_t -р tcp 81
После этого проверил список портов командой
semanage port -l | grep http_port_t
Убедился, что порт 81 появился в списке.

![Рисунок17](image/k17.jpg)

20. Попробовал запустить веб-сервер Apache ещё раз. Запустился.

21. Вернул контекст httpd_sys_cоntent__t к файлу /var/www/html/ test.html:
chcon -t httpd_sys_content_t /var/www/html/test.html
После этого попробовал получить доступ к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1:81/test.html.
Получил слово test

22. Исправил обратно конфигурационный файл apache, вернув Listen 80.

23. Удалил привязку http_port_t к 81 порту: semanage port -d -t http_port_t -p tcp 81 и проверил, что порт 81 удалён.

![Рисунок18](image/k18.jpg)

26. Удалил файл /var/www/html/test.html: rm /var/www/html/test.html

![Рисунок19](image/k19.jpg)

# Выводы

Я развил навыки администрирования ОС Linux. Получил первое практическое знакомство с технологией SELinux1. Проверил работу SELinx на практике совместно с веб-сервером Apache.


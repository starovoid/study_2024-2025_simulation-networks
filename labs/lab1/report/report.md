---
## Front matter
title: "Лабораторнаяя работа №1. Введение в Mininet"
author: "Старовойтов Егор Сергеевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

<!--## Bibliography-->
<!--bibliography: bib/cite.bib-->
<!--csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl-->
<!---->
<!--## Pdf output format-->
<!--toc: true # Table of contents-->
<!--toc-depth: 2-->
<!--lof: true # List of figures-->
<!--lot: true # List of tables-->
<!--fontsize: 12pt-->
<!--linestretch: 1.5-->
<!--papersize: a4-->
<!--documentclass: scrreprt-->
<!--## I18n polyglossia-->
<!--polyglossia-lang:-->
<!--  name: russian-->
<!--  options:-->
<!--	- spelling=modern-->
<!--	- babelshorthands=true-->
<!--polyglossia-otherlangs:-->
<!--  name: english-->
<!--## I18n babel-->
<!--babel-lang: russian-->
<!--babel-otherlangs: english-->
<!--## Fonts-->
<!--mainfont: IBM Plex Serif-->
<!--romanfont: IBM Plex Serif-->
<!--sansfont: IBM Plex Sans-->
<!--monofont: IBM Plex Mono-->
<!--mathfont: STIX Two Math-->
<!--mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94-->
<!--romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94-->
<!--sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94-->
<!--monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9-->
<!--mathfontoptions:-->
<!--## Biblatex-->
<!--biblatex: true-->
<!--biblio-style: "gost-numeric"-->
<!--biblatexoptions:-->
<!--  - parentracker=true-->
<!--  - backend=biber-->
<!--  - hyperref=auto-->
<!--  - language=auto-->
<!--  - autolang=other*-->
<!--  - citestyle=gost-numeric-->
<!--## Pandoc-crossref LaTeX customization-->
<!--figureTitle: "Рис."-->
<!--tableTitle: "Таблица"-->
<!--listingTitle: "Листинг"-->
<!--lofTitle: "Список иллюстраций"-->
<!--lotTitle: "Список таблиц"-->
<!--lolTitle: "Листинги"-->
<!--## Misc options-->
<!--indent: true-->
<!--header-includes:-->
<!--  - \usepackage{indentfirst}-->
<!--  - \usepackage{float} # keep figures where there are in the text-->
<!--  - \floatplacement{figure}{H} # keep figures where there are in the text-->
<!------->

# Цель работы
Основной целью работы является развёртывание в системе виртуализации
(например, в VirtualBox) mininet, знакомство с основными командами для рабо-
ты с Mininet через командную строку и через графический интерфейс.

# Теоретическое введение
Mininet (http://mininet.org/) — это виртуальная среда, которая позволяет
разрабатывать и тестировать сетевые инструменты и протоколы. В сетях Mininet
работают реальные сетевые приложения Unix/Linux, а также реальное ядро Linux
и сетевой стек.

# Выполнение лабораторной работы

## 1. Настройка и первый запуск VM Mininet.
Помимо очевидных действий пришлось добавить видеопамяти виртуальной машине и настроить сетевой адаптер в параметров VirtualBox.

![Настройка и первый запуск VM Mininet](image/Screenshot_1.png)

## 2. Подключение к VM по ssh 
![Подключение к VM по ssh](image/Screenshot_2.png)

## 3. Настройка сети.
![Настройка сети](image/Screenshot_3.png)

## 4. Настройка 01-netcfg.yaml
![Настройка 01-netcfg.yaml](image/Screenshot_4.png)

## 5. Обновление Mininet
![Обновление Mininet](image/Screenshot_5.png)

## 6. Настройка xterm
![Настройка xterm](image/Screenshot_6.png)

## 7. Основы работы c Mininet
![Основы работы c Mininet](image/Screenshot_7.png)

## 8. Проверка связности
Предварительно пришлось повозиться и установить+настроить, чтобы иметь возможность запускать графические приложения.

![Проверка связности](image/Screenshot_8.png)

## 9. Топология сети
![Топология сети](imahe/Screenshot_9.png)

## 10. ifconfig на хостах
Приведу скриншот для хоста "h1", "h2" выглядит по аналогии.

![ifconfig на h1](image/Screenshot_10.png)

## 11. ifconfig на h1 после автоматического назначения айпи адресов
![ifconfig на h1](image/Screenshot_11.png)

## 12. Сохранение работы
![Сохранение работы](image/Screenshot_12.png)


# Выводы
Я успешно развернул mininet в среде виртуализации VirtualBox и познакомился с основными командами работы с Mininet через командную оболочку и графический интерфейс.


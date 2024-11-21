---
## Front matter
title: "Лабораторная работа № 2"
subtitle: "Измерение и тестирование пропускной способности сети. Интерактивный эксперимент"
author: "Старовойтов Егор Сергеевич"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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
Основной целью работы является знакомство с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получение навыков проведения интерактивного эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

# Задание
1. Установить на виртуальную машину mininet iPerf3 и дополнительное про-
граммное обеспечения для визуализации и обработки данных.
2. Провести ряд интерактивных экспериментов по измерению пропускной
способности с помощью iPerf3 с построением графиков.


# Теоретическое введение
В контексте сеанса связи между двумя конечными устройствами на сетевом
пути под пропускной способностью (throughput) понимается скорость в битах
в секунду, с которой процесс-отправитель может доставлять данные процессу-
получателю. В тоже время под полосой пропускания (Bandwidth) понимается
физическое свойство среды передачи данных, зависящее, например, от конструк-
ции и длины провода или волокна. Иногда термины «пропускная способность»
(throughput) и «полоса пропускания» (bandwidth) используются взаимозаменяе-
мо.

iPerf3 (сайт: https://iperf.fr/; лицензия: three-clause BSD license;
репозиторий: https://github.com/esnet/iperf) представляет собой крос-
сплатформенное клиент-серверное приложение с открытым исходным кодом,
которое можно использовать для измерения пропускной способности между
двумя конечными устройствами.

iPerf3 может работать с транспортными протоколами TCP, UDP и SCTP:
– TCP и SCTP:
– измеряет пропускную способность;
– позволяет задать размер MSS/MTU;
– отслеживает размер окна перегрузки TCP (CWnd).
– UDP:
– измеряет пропускную способность;
– измеряет потери пакетов;
– измеряет колебания задержки (jitter);
– поддерживает групповую рассылку пакетов (multicast).

Пользователь взаимодействует с iPerf3 с помощью команды iperf3. Основной
синтаксис iperf3, используемый как на клиенте, так и на сервере, выглядит
следующим образом:

```bash
iperf3 [-s|-c] [options]
```

Здесь -s — запуск сервера; -c — запуск клиента. Описание опций можно
посмотреть, введя команду iperf3 -h.
iPerf3 позволяет экспортировать результаты теста в файл с облегчённым
форматом обмена данными JSON (JavaScript Object Notation, нотация объек-
тов JavaScript), что позволяет другим приложениям легко анализировать файл
и интерпретировать результаты.
Для визуализации результатов измерения iPerf3 можно использовать па-
кет iperf3_plotter. Репозиторий https://github.com/ekfoury/iperf3_
plotter содержит следующие скрипты:
– preprocessor.sh: преобразует файл JSON iPerf3 в файл значений, разделён-
ных запятыми (CSV); использует AWK для форматирования полей файла;
– plot_iperf.sh: принимает JSON-файл iPerf3, вызывает препроцессор
и gnuplot для создания выходных PDF-файлов


# Выполнение лабораторной работы
### 1. Подключение, просмотр адресов, обновление пакетов 
![Screenshot 1](image/Screenshot_21-Nov_19-31-27_46.png)

### 2. Установка iperf
![Screenshot 2](image/Screenshot_21-Nov_19-32-18_9991.png)

### 3. Устанвока дополнительного ПО
![Screenshot 3](image/Screenshot_21-Nov_19-33-13_24780.png)

### 4. Развертка iperf3_plotter
![Screenshot 4](image/Screenshot_21-Nov_19-34-25_18908.png)

### 5. Параметры запущенной топологии
![Screenshot 5](image/Screenshot_21-Nov_19-43-39_2271.png)

### 6. Запуск сервера iPerf3 в терминале h2 
Запуск осуществлялся командой
```bash 
iperf3 -s on h2
```

![Screenshot 6](image/Screenshot_21-Nov_20-17-38_27313.png)

### 7. Тест соединения с терминала h1 
Запуск осуществлялся командой
```bash 
iperf3 -c 10.0.0.2
```

Здесь параметр -c указывает, что хост h1 настроен как клиент, а параметр
10.0.0.2 является IP-адресом сервера iPerf3 (хост h2).

Полученный сводный отчет содержит следующие данные:

- ID: идентификационный номер соединения.
- интервал (Interval): временной интервал для периодических отчетов
о пропускной способности (по умолчанию временной интервал равен 1
секунде);
- передача (Transfer): сколько данных было передано за каждый интервал
времени;
- пропускная способность (Bitrate): измеренная пропускная способность
в каждом временном интервале;
- Retr: количество повторно переданных TCP-сегментов за каждый вре-
менной интервал (это поле увеличивается, когда TCP-сегменты теряются
в сети из-за перегрузки или повреждения);
- Cwnd: указывает размер окна перегрузки в каждом временном интер-
вале (TCP использует эту переменную для ограничения объёма данных,
которые TCP-клиент может отправить до получения подтверждения от-
правленных данных). интервал (Interval): временной интервал для периодических отчетов
о пропускной способности (по умолчанию временной интервал равен 1
секунде);
- передача (Transfer): сколько данных было передано за каждый интервал
времени;
- пропускная способность (Bitrate): измеренная пропускная способность
в каждом временном интервале;
- Retr: количество повторно переданных TCP-сегментов за каждый вре-
менной интервал (это поле увеличивается, когда TCP-сегменты теряются
в сети из-за перегрузки или повреждения);
- Cwnd: указывает размер окна перегрузки в каждом временном интер-
вале (TCP использует эту переменную для ограничения объёма данных,
которые TCP-клиент может отправить до получения подтверждения от-
правленных данных).

![Screenshot 7](image/Screenshot_21-Nov_20-19-07_26194.png)

### 8. Эксперимент с прерыванеим (командой "killall")
![Screenshot 8](image/Screenshot_21-Nov_20-21-54_2076.png)

### 9. Тест пропускной способности с интервалом 2 сек
![Screenshot 9](image/Screenshot_21-Nov_20-27-48_29247.png)

### 10. Тест с объемом данных 16G
![Screenshot 10](image/Screenshot_21-Nov_20-29-17_31909.png)

### 11. Тест UDP
![Screenshot 11](image/Screenshot_21-Nov_20-31-13_9326.png)

### 12. Тест с портом -p 3250
![Screenshot 12](image/Screenshot_21-Nov_20-33-18_5543.png)

### 13. Тест с опцией -1. 
Действительно видно, что сервер останавливается после теста первого и единственного соединения.

![Screenshot 13](image/Screenshot_21-Nov_20-34-45_5674.png)

### 14. Вывод результатов теста в Json
![Screenshot 14](image/Screenshot_21-Nov_20-36-46_14121.png)

### 15. Экспорт результатов теста в Json файл в рабочем каталоге
![Screenshot 15](image/Screenshot_21-Nov_20-38-24_6455.png)

### 16. Визуализация графиков
![Screenshot 16](image/Screenshot_21-Nov_20-41-53_3332.png)


## Графики

![bytes](results/bytes.png)

![cwnd](results/cwnd.png)

![MTU](results/MTU.png)

![retransmits](results/retransmits.png)

![RTT](results/RTT.png)

![RTT_Var](results/RTT_Var.png)

![throughput](results/throughput.png)







# Выводы
Я ознакомился с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получил навыки проведения интерактивного эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

В процессе выполнения работы были решены поставленные задачи, а именно:
1. iPerf3 и дополнительное ПО было установлено на виртуальную машину с mininet.
2. Был проведен ряд интерактивных экспериментов по измерению пропускной способности; были построены графики.

# Список литературы{.unnumbered}


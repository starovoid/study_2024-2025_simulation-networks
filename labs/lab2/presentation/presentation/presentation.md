---
## Front matter
lang: ru-RU
title: Лабораторная работа № 2
subtitle: Измерение и тестирование пропускной способности сети. Интерактивный эксперимент
author:
  - Старовойтов Е. С.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 21 ноября 2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация

## Докладчик

  * Старовойтов Егор Сергеевич 
  * студент кафедры ТВиК
  * Российский университет дружбы народов
  * [1032212281@pfur.ru](mailto:1032212281@pfur.ru)


# Вводная часть

## Цели и задачи
Основной целью работы является знакомство с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получение навыков проведения интерактивного эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

Задачи:
1. Установить на виртуальную машину mininet iPerf3 и дополнительное про-
граммное обеспечения для визуализации и обработки данных.
2. Провести ряд интерактивных экспериментов по измерению пропускной
способности с помощью iPerf3 с построением графиков.


## Результаты
Поставленные боевые задачи были выполнены, все цели достигнуты.

# Выполнение работы

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



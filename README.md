# Домашняя работа "Динамическая маршрутизация OSPF"

<details>
<summary>Введение</summary>

OSPF — протокол динамической маршрутизации, использующий концепцию разделения на области в целях масштабирования.
Административная дистанция OSPF — 110  
Основные свойства протокола OSPF:  
+ Быстрая сходимость  
+ Масштабируемость (подходит для маленьких и больших сетей)  
+ Безопасность (поддежка аутентиикации)  
+ Эффективность (испольование алгоритма поиска кратчайшего пути)  
При настроенном OSPF маршрутизатор формирует таблицу топологии с использованием результатов вычислений, основанных на алгоритме кратчайшего пути (SPF) Дейкстры. Алгоритм поиска кратчайшего пути основывается на данных о совокупной стоимости доступа к точке назначения. Стоимость доступа определятся на основе скорости интерфейса.  
Чтобы повысить эффективность и масштабируемость OSPF, протокол поддерживает иерархическую маршрутизацию с помощью областей (area).  
Область OSPF (area) — Часть сети, которой ограничивается формирование базы данных о состоянии каналов. Маршрутизаторы, находящиеся в одной и той же области, имеют одну и ту же базу данных о топологии сети. Для определения областей применяются идентификаторы областей.  
Протоколы OSPF бвывают 2-х версий:  
+ OSPFv2  
+ OSPFv3  
Основным отличием протоколов является то, что OSPFv2 работает с IPv4, а OSPFv3 — c IPv6.
Маршрутизаторы в OSPF классифицируются на основе выполняемой ими функции:  

 ![Альтернативный текст](https://i.ibb.co/dp9Zffd/1234.png)

+ Internal router (внутренний маршрутизатор) — маршрутизатор, все интерфейсы которого находятся в одной и той же области.  
+ Backbone router (магистральный маршрутизатор) — это маршрутизатор, который находится в магистральной зоне (area 0).  
+ ABR (пограничный маргрутизатор области) — маршрутизатор, интерфейсы которого подключены к разным областям.
+ ASBR (Граничный маршрутизатор автономной системы) — это маршрутизатор, у которого интерфейс подключен к внешней сети.  
Также с помощью OSPF можно настроить ассиметричный роутинг.  
Ассиметричная маршрутизация — возможность пересекать сеть в одном направлении, используя один путь, и возвращаться через другой путь.  

</details>

<details>
<summary>Цели</summary>

Создать домашнюю сетевую лабораторию. Научится настраивать протокол OSPF в Linux-based системах.

</details>

<details>
<summary>Описание ДЗ</summary>

1. Развернуть 3 виртуальные машины  
2. Объединить их разными vlan  
- настроить OSPF между машинами на базе Quagga;  
- изобразить ассиметричный роутинг;  
- сделать один из линков "дорогим", но что бы при этом роутинг был симметричным.  
Формат сдачи: Vagrantfile + ansible  

</details>
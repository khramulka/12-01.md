# Домашнее задание к занятию «Базы данных» - «Храмов Александр»
 



---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

- #### ОТВЕТ:
ТАБЛИЦЫ:
1. **сотрудники** (
 - идентификатор сотрудника, первичный ключ, SERIAL,
 - Ф.И.О. VARCHAR(50),
 - дата найма DATE,
 - оклад DECIMAL(10,2),
 - идентификатор должности, внешний ключ, INTEGER,
 - идентификатор структурного подразделения, внешний ключ, INTEGER)
2. **тип подразделения** (
 - идентификатор типа подразделения, первичный ключ, SERIAL,
 - тип подразделения VARCHAR(20))
3. **структурное подразделение** (
 - идентификатор структурного подразделения, первичный ключ, SERIAL,
 - структурное подразделение VARCHAR(60),
 - идентификатор типа подразделения, внешний ключ, INTEGER
 - идентификатор филиала, внешний ключ, INTEGER)
4. **адрес филиала** (
 - идентификатор филиала, первичный ключ, SERIAL,
 - адрес филиала VARCHAR(60))
5. **должность** (
 - идентификатор должности, первичный ключ, SERIAL,
 - должность VARCHAR(50))
6. **проект** (
 - идентификатор проекта, первичный ключ, SERIAL,
 - название проекта VARCHAR(30))
7. **назначение на проект** (
 - идентификатор сотрудника, внешний ключ, INTEGER,
 - идентификатор проекта, внешний ключ, INTEGER,)
---

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.


### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.

#### ОТВЕТ:

1. Тип подразделения и структурное подразделение - функциональные зависимости;
2. Привести поле "проект" в атомарный вид, выделить в отдельную таблицу адрес филиала, создать первичный ключ для первой таблицы.


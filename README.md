
# sql-ex.exercises

## БД. Схема 1

![](https://github.com/klimovich-anton/sql-ex.exercises/blob/main/data_schema/db_1_computer_firm.png)

### Задача 1
Найдите номер модели, скорость и размер жесткого диска для всех ПК стоимостью менее 500 дол. Вывести: model, speed и hd
#### Решение 1
```sql
select model, speed, hd from pc
where price < 500;
```

### Задача 2
Найдите производителей принтеров. Вывести: maker
#### Решение 2
```sql
select distinct maker from product
where type = 'printer';
```
### Задача 3
Найдите номер модели, объем памяти и размеры экранов ПК-блокнотов, цена которых превышает 1000 дол.

#### Решение 3
```sql
select model, ram, screen from laptop
where price > 1000;
```

### Задача 4
Найдите все записи таблицы Printer для цветных принтеров.

#### Решение 4
```sql
select * from Printer
where color = 'y';
```

### Задача 5
Найдите номер модели, скорость и размер жесткого диска ПК, имеющих 12x или 24x CD и цену менее 600 дол.
#### Решение 5

``` sql
SELECT model, speed, hd from pc
where price < 600 and (cd='12x' or cd='24x');
```
##### Примечание 5
Изначально под размером понимал параметр RAM, то есть столбец с объемом памяти.
Не был знаком с предикатом ```BETWEEN```, на форуме предложено иное решение задачи:
``` sql
SELECT model, speed, hd
FROM PC
WHERE price < 600 AND 
cd BETWEEN '12x' AND '24x';
```
На курсах постоянно объясняют - не важен синтаксис кода, важно как он работает. Если не откровенный костыль конечно. В моём случае отработал.

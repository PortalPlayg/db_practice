## возвращает идентификатор меню и названия пиццы

![](1.1_13.PNG)
![](1.2_13.PNG)
```
SELECT id, pizza_name FROM menu
UNION
SELECT id, name FROM person ORDER BY id, pizza_name

```
## измените порядок по имени объекта для части данных из таблица person, а затем из таблицы меню

![](2.1_13.PNG)
![](2.2_13.PNG)

```
SELECT name,'person' AS sourece FROM person
UNION ALL
SELECT pizza_name, 'menu' AS source FROM menu ORDER BY source,name

```

## который возвращает общие строки для атрибутов.order_date, person_id из таблицы person_order с одной стороны и visit_date,person_id из таблицы person_visits с другой стороны

![](3_13.PNG)

```
SELECT person_id, order_date AS action_date FROM person_order
INTERSECT
SELECT person_id, visit_date AS action_date FROM person_visits
ORDER BY action_date , person_id DESC
```

##оператор , который возвращает разницу (минус) person_id.


![](4_13.PNG)

```
SELECT person_id FROM person_order WHERE order_date = '2022-01-07'
EXCEPT ALL
SELECT person_id FROM person_visits WHERE visit_date = '2022-01-07'

```

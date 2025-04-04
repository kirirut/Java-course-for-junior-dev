**Пример**

Выбрать названия и количества тех книг, количество которых от 5 до 14 включительно.

_Запрос:_

```sql
SELECT title, amount 
FROM book
WHERE amount BETWEEN 5 AND 14;
```

Оператор  `IN`  позволяет выбрать данные, соответствующие значениям из списка.

**Пример**
Выбрать названия и цены книг, написанных Булгаковым или Достоевским.
_Запрос:_

```sql
SELECT title, price 
FROM book
WHERE author IN ('Булгаков М.А.', 'Достоевский Ф.М.');
```

## Задание

Вывести название и авторов тех книг, цены которых принадлежат интервалу от 540.50 до 800 (включая границы),  а количество или 2, или 3, или 5, или 7 .

_Результат:_

```sql
+--------------------+------------------+
| title              | author           |
+--------------------+------------------+
| Мастер и Маргарита | Булгаков М.А.    |
| Белая гвардия      | Булгаков М.А.    |
| Братья Карамазовы  | Достоевский Ф.М. |
+--------------------+------------------+
```

_***Запрос:***_

```sql
SELECT title, author 
FROM book
WHERE price BETWEEN 540.50 AND 800
  AND amount IN (2, 3, 5, 7);
```

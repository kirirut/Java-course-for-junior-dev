Оператор `LIKE` используется для сравнения строк. В отличие от операторов отношения равно (**=**) и не равно (**<>**), `LIKE` позволяет сравнивать строки не на полное совпадение (не совпадение), а в соответствии с шаблоном. Шаблон может включать **обычные символы** и **символы-шаблоны**. При сравнении с шаблоном, его обычные символы должны в точности совпадать с символами, указанными в строке. Символы-шаблоны могут совпадать с произвольными элементами символьной строки.

| Символ-шаблон         | Описание                                         | Пример                                                                                                                                       |
| --------------------- | ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **%**                 | Любая строка, содержащая ноль или более символов | `SELECT * FROM book WHERE author LIKE '%М.%'`  <br>выполняет поиск и выдает все книги, инициалы авторов которых содержат «_М._»              |
| **_** (подчеркивание) | Любой одиночный символ                           | `SELECT * FROM book WHERE title LIKE 'Поэм_'`  <br>выполняет поиск и выдает все книги, названия которых либо «_Поэма_», либо «_Поэмы_» и пр. |
**Пример 1**

Вывести названия книг, начинающихся с буквы «_Б_».

_Запрос:_

```sql
SELECT title 
FROM book
WHERE title LIKE 'Б%';
/* эквивалентное условие 
title LIKE 'б%'
*/
```

_Результат:_

```sql
+-------------------+
| title             |
+-------------------+
| Белая гвардия     |
| Братья Карамазовы |
+-------------------+
```


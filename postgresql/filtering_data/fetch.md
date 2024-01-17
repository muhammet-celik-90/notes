# FETCH

To skip a certain number of rows and retrieve a specific number of rows, you often use the LIMIT clause in the SELECT statement. (*Belirli sayıda satırı atlamak ve belirli sayıda satırı almak için sıklıkla SELECT deyiminde LIMIT yan tümcesini kullanırsınız.*)

The LIMIT clause is widely used by many Relational Database Management Systems such as MySQL, H2, and HSQLDB. However, the LIMIT clause is not a SQL standard. (*LIMIT cümlesi MySQL, H2 ve HSQLDB gibi birçok İlişkisel Veritabanı Yönetim Sistemi tarafından yaygın olarak kullanılmaktadır. Ancak LIMIT yan tümcesi bir SQL standardı değildir.*)

To conform with the SQL standard, PostgreSQL supports the FETCH clause to skip a certain number of rows and then fetch a specific number of rows. (*SQL standardına uymak için PostgreSQL, belirli sayıda satırı atlamak ve ardından belirli sayıda satırı getirmek için FETCH yan tümcesini destekler.*)

*Syntax*

```javascript
OFFSET row_to_skip { ROW | ROWS }
FETCH { FIRST | NEXT } [ row_count ] { ROW | ROWS } ONLY
```

The row_count must be an integer 1 or greater. The row_count defaults to 1. (*Row_count'un 1 veya daha büyük bir tamsayı olması gerekir. Row_count varsayılan olarak 1'dir.*)

## FETCH vs. LIMIT

The FETCH clause is functionally equivalent to the LIMIT clause. If you plan to make your application compatible with other database systems, you should use the FETCH clause because it follows the standard SQL. (*FETCH yan tümcesi işlevsel olarak LIMIT yan tümcesine eşdeğerdir. Uygulamanızı diğer veritabanı sistemleriyle uyumlu hale getirmeyi planlıyorsanız standart SQL'i takip ettiği için FETCH deyimini kullanmalısınız.*)

*Examples:*

```javascript
SELECT
    film_id,
    title
FROM
    film
ORDER BY
    title 
FETCH FIRST 5 ROW ONLY;
```

```javascript
 film_id |      title
---------+------------------
       1 | Academy Dinosaur
       2 | Ace Goldfinger
       3 | Adaptation Holes
       4 | Affair Prejudice
       5 | African Egg
(5 rows)
```

*query:*

```javascript
SELECT
    film_id,
    title
FROM
    film
ORDER BY
    title 
OFFSET 5 ROWS 
FETCH FIRST 5 ROW ONLY; 
```

*output:*

```javascript
 film_id |      title
---------+------------------
       6 | Agent Truman
       7 | Airplane Sierra
       8 | Airport Pollock
       9 | Alabama Devil
      10 | Aladdin Calendar
(5 rows)
```





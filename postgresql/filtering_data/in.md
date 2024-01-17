# IN

The IN operator allows you to check whether a value matches any value in a list of values. (*IN operatörü, bir değerin, değerler listesindeki herhangi bir değerle eşleşip eşleşmediğini kontrol etmenizi sağlar.*)

*Syntax:*

```javascript
value IN (value1,value2,...)
```

The IN operator returns true if the value is equal to any value in the list. (*IN operatörü, değer listedeki herhangi bir değere eşitse true değerini döndürür*)

*Example:*

```javascript
SELECT
  film_id, 
  title 
FROM
  film 
WHERE
  film_id in (1, 2, 3);
```

OR

```javascript
SELECT 
  film_id, 
  title 
FROM 
  film 
WHERE 
  film_id = 1 
  OR film_id = 2 
  OR film_id = 3;
```

*Output:*

```javascript
 film_id |      title
---------+------------------
       1 | Academy Dinosaur
       2 | Ace Goldfinger
       3 | Adaptation Holes
(3 rows)
```

The query that uses the IN operator is shorter and more readable than the query that uses equal (=) and OR operators.

Additionally, PostgreSQL executes the query with the IN operator much faster than the same query that uses a list of OR operators.


## CAST OPERATOR (::)

cast them to date values that have the date part only

*Syntax:*

```javascript

payment_date::date

```
For example, if the timestamp value is 2007-02-15 22:25:46.996577, the cast operator will convert it to 2007-02-15.

## NOT IN

*Syntax:*

```javascript

value NOT IN (value1, value2, ...)

```

*Example: *

```javascript

SELECT 
  film_id, 
  title 
FROM 
  film 
WHERE 
  film_id NOT IN (1, 2, 3) 
ORDER BY 
  film_id;

```


```javascript

 film_id |            title
---------+-----------------------------
       4 | Affair Prejudice
       5 | African Egg
       6 | Agent Truman
       7 | Airplane Sierra
       8 | Airport Pollock
...

```





# WHERE

is used for filtering rows. (*satırları filtrelemek için kullanılır*)

*Example expression:*

```javascript

SELECT select_list
FROM table_name
WHERE condition
ORDER BY sort_expression

```

![flow](https://www.postgresqltutorial.com/wp-content/uploads/2020/07/PostgreSQL-WHERE.png)

If you use column aliases in the SELECT clause, you cannot use them in the WHERE clause. (*SELECT yan tümcesinde sütun takma adları kullanırsanız, bunları WHERE yan tümcesinde kullanamazsınız.*)

| Operator   | Description                                                     |
|:---------- | :---------------------------------------------------------------|
| =          | Equal                                                           |
| >          | Greater than                                                    |
| <          | Less than                                                       |
| >=         | Greater than or equal                                           |
| <=         | Less than or equal                                              |
| <> or !=   | Not equal                                                       |
| AND        | Logical operator AND                                            |
| OR         | Logical operator OR                                             |
| IN         | Return true if a value matches any value in a list              |
| BETWEEN    | Return true if a value is between a range of values             |
| LIKE       | Return true if a value matches a pattern                        |
| IS NULL    | Return true if a value is NULL                                  |
| NOT        | Negate the result of other operators                            |


*Example:*

```javascript

SELECT
	last_name,
	first_name
FROM
	customer
WHERE
	first_name = 'Jamie';

```

### AND / OR

```javascript

SELECT
	last_name,
	first_name
FROM
	customer
WHERE
	first_name = 'Jamie' AND 
        last_name = 'Rice';

```

### IN

If you want to match a string with any string in a list, you can use the IN operator. (*Bir dizeyi listedeki herhangi bir dizeyle eşleştirmek istiyorsanız IN operatörünü kullanabilirsiniz.*)

```javascript

SELECT
	first_name,
	last_name
FROM
	customer
WHERE 
	first_name IN ('Ann','Anne','Annie');

```

*Output:*

![output](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/PostgreSQL-WHERE-with-IN-operator.png)

### LIKE

To find a string that matches a specified pattern, you use the LIKE operator. (*Belirtilen kalıpla eşleşen bir dize bulmak için LIKE operatörünü kullanırsınız*)

```javascript

SELECT
	first_name,
	last_name
FROM
	customer
WHERE 
	first_name LIKE 'Ann%'

```

![output](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/PostgreSQL-WHERE-with-LIKE-operator.png)


### BETWEEN

The BETWEEN operator returns true if a value is in a range of values. (*BETWEEN operatörü, bir değer belirli bir aralıktaysa true değerini döndürür.*)


```javascript
SELECT
	first_name,
	LENGTH(first_name) name_length
FROM
	customer
WHERE 
	first_name LIKE 'A%' AND
	LENGTH(first_name) BETWEEN 3 AND 5
ORDER BY
	name_length;

```

### NOT EQUAL OPERATOR (<>)

This example finds customers whose first names start with Bra and last names are not Motley: (*Bu örnek, adları Bra ile başlayan ve soyadları Motley olmayan müşterileri bulur:*)

```javascript
SELECT 
	first_name, 
	last_name
FROM 
	customer 
WHERE 
	first_name LIKE 'Bra%' AND 
	last_name <> 'Motley';
```
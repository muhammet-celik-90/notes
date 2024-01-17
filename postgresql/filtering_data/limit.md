# LIMIT

```javascript
SELECT select_list 
FROM table_name
ORDER BY sort_expression
LIMIT row_count
```

 If row_count is zero, the query returns an empty set. 

 In case row_count is NULL, the query returns the same result set as it does not have the LIMIT clause. (*row_count'un NULL olması durumunda sorgu, LIMIT yan tümcesine sahip olmadığından aynı sonuç kümesini döndürür.*)

 ## OFFSET

 In case you want to skip a number of rows (*Eğer birkaç satırı atlamak istersek OFFSET'i kullanabiliriz*)

 *Example:*

 *Normal query:*

 ```javascript
SELECT
	film_id,
	title,
	release_year
FROM
	film
ORDER BY
	film_id
LIMIT 5;
```

![result](https://www.postgresqltutorial.com/wp-content/uploads/2020/07/PostgreSQL-LIMIT-Select-First-n-Rows.png)

*OFFSET query:*

```javascript
SELECT
	film_id,
	title,
	release_year
FROM
	film
ORDER BY
	film_id
LIMIT 4 OFFSET 3;
```

![result2](https://www.postgresqltutorial.com/wp-content/uploads/2020/07/PostgreSQL-LIMIT-OFFSET-example.png)



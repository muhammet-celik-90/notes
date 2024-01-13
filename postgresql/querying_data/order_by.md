# ORDER BY

The ORDER BY clause allows you to sort rows in ascending or descending order based on a sort expression. (*ORDER BY cümlesi, sıralama ifadesine göre satırları artan veya azalan düzende sıralamanıza olanak tanır.*)

`ASC` -> is default.

```javascript

SELECT
	select_list
FROM
	table_name
ORDER BY
	sort_expression1 [ASC | DESC],
        ...
	sort_expressionN [ASC | DESC];

```

## ORDER BY clause to sort rows by expressions

The LENGTH() function accepts a string and returns the length of that string. (*LENGTH() işlevi bir dizeyi kabul eder ve bu dizenin uzunluğunu döndürür.*)

```javascript

SELECT 
	first_name,
	LENGTH(first_name) len
FROM
	customer
ORDER BY 
	len DESC;

```

*Output:*

![çıktı](https://www.postgresqltutorial.com/wp-content/uploads/2019/12/PostgreSQL-ORDER-BY-expressions.png)


## ORDER BY clause and NULL

When you sort rows that contains NULL, you can specify the order of NULL with other non-null values by using the NULLS FIRST or NULLS LAST option of the ORDER BY clause: (*NULL içeren satırları sıraladığınızda, ORDER BY yan tümcesinin NULLS FIRST veya NULLS LAST seçeneğini kullanarak NULL'un diğer null olmayan değerlerle sırasını belirtebilirsiniz:*)

```javascript

ORDER BY sort_expresssion [ASC | DESC] [NULLS FIRST | NULLS LAST]

```







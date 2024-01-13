# DISTINCT

is used to remove to duplicate rows from result. (*Tekrar eden satırları çıkarmak için kullanılır*)

*Example expression:*

```javascript

SELECT
   DISTINCT column1
FROM
   table_name;

```


For multiple column, separate columns with comma (,). (*Birden fazla sütun yazacaksak, sütunları virgül (,) ile birbirinden ayırmalıyız.*)


#### Example

*Example Database*

![example_img](https://www.postgresqltutorial.com/wp-content/uploads/2020/07/PostgreSQL-Distinct-Sample-Table.png)

```javascript

SELECT
	DISTINCT bcolor
FROM
	distinct_demo
ORDER BY
	bcolor;

```

*Output:*

![output](https://www.postgresqltutorial.com/wp-content/uploads/2020/07/PostgreSQL-Distinct-select-distinct-one-column.png)



### DISTINCT multiple columns

```javascript

SELECT
	DISTINCT bcolor,
	fcolor
FROM
	distinct_demo
ORDER BY
	bcolor,
	fcolor;

```

*Output:*

![output](https://www.postgresqltutorial.com/wp-content/uploads/2020/07/PostgreSQL-Distinct-select-distinct-two-columns.png)

Because we specified both bcolor and fcolor columns in the SELECT DISTINCT clause, PostgreSQL combined the values in both bcolor and fcolor columns to evaluate the uniqueness of the rows. (*SELECT DISTINCT cümlesinde hem bcolor hem de fcolor sütunlarını belirttiğimizden, PostgreSQL, satırların benzersizliğini değerlendirmek için hem bcolor hem de fcolor sütunlarındaki değerleri birleştirdi.*)


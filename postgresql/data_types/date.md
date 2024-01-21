# DATE

PostgreSQL uses 4 bytes to store a date value.

When storing a date value, PostgreSQL uses the  yyyy-mm-dd format e.g., 2000-12-31. It also uses this format for inserting data into a date column.

If you create a table that has a DATE column and you want to use the current date as the default value for the column, you can use the CURRENT_DATE after the DEFAULT keyword.

## DATE functions

#### Get the current date

To get the current date and time, you use the built-in NOW() function. However, to get the date part only (without the time part), you use the double colons (::) to cast a DATETIME value to a DATE value.

The following statement returns the current date of the database server:

```javascript
SELECT NOW()::date;
```

Another way to get current date is to use the CURRENT_DATE as follows:

```javascript
SELECT CURRENT_DATE;
```

#### Output a PostgreSQL date value in a specific format

To output a date value in a specific format, you use the TO_CHAR() function. The TO_CHAR() function accepts two parameters. The first parameter is the value that you want to format, and the second one is the template that defines the output format.

For example, to display the current date in dd/mm/yyyy format, you use the following statement:

```javascript
SELECT TO_CHAR(NOW() :: DATE, 'dd/mm/yyyy');
```

```javascript
  to_char
------------
 23/06/2016
(1 row)
```

Or to display a date in the format like Jun 22, 2016, you use the following statement:

```javascript
SELECT TO_CHAR(NOW() :: DATE, 'Mon dd, yyyy');
```

#### Get the interval between two dates

To get the interval between two dates, you use the minus (-) operator.  

#### Calculate ages in years, months, and days

To calculate age at the current date in years, months, and days, you use the AGE() function.

The following statement uses the AGE() function to calculate the ages of employees in the employees table.

```javascript
SELECT
	employee_id,
	first_name,
	last_name,
	AGE(birth_date)
FROM
	employees;
```

```javascript
 employee_id | first_name | last_name |           age
-------------+------------+-----------+-------------------------
           1 | Shannon    | Freeman   | 36 years 5 mons 22 days
           2 | Sheila     | Wells     | 38 years 4 mons 18 days
           3 | Ethel      | Webb      | 41 years 5 mons 22 days
(3 rows)
```

#### Extract year, quarter, month, week, day from a date value

To get the year, quarter, month, week, day from a date value, you use the EXTRACT() function.

```javascript
SELECT
	employee_id,
	first_name,
	last_name,
	EXTRACT (YEAR FROM birth_date) AS YEAR,
	EXTRACT (MONTH FROM birth_date) AS MONTH,
	EXTRACT (DAY FROM birth_date) AS DAY
FROM
	employees;
```

```javascript
 employee_id | first_name | last_name | year | month | day
-------------+------------+-----------+------+-------+-----
           1 | Shannon    | Freeman   | 1980 |     1 |   1
           2 | Sheila     | Wells     | 1978 |     2 |   5
           3 | Ethel      | Webb      | 1975 |     1 |   1
(3 rows)
```
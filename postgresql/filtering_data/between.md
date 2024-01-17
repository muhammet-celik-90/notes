# BETWEEN

The BETWEEN operator allows you to check if a value falls within a range of values.

*Syntax*

```javascript

value BETWEEN low AND high;

```

*Example:*

```javascript

SELECT 
  payment_id, 
  amount 
FROM 
  payment 
WHERE 
  payment_id BETWEEN 17503 AND 17505 
ORDER BY 
  payment_id;

```

*Output:*

```javascript

 payment_id | amount
------------+--------
      17503 |   7.99
      17504 |   1.99
      17505 |   7.99
(3 rows)

```

## NOT BETWEEN

```javascript
SELECT 
  payment_id, 
  amount 
FROM 
  payment 
WHERE 
  payment_id NOT BETWEEN 17503 AND 17505 
ORDER BY 
  payment_id;
```

```javascript

payment_id | amount
------------+--------
      17506 |   2.99
      17507 |   7.99
      17508 |   5.99
      17509 |   5.99
      17510 |   5.99
...

```

## BETWEEN with a date range

If you want to check a value against a date range, you use the literal date in ISO 8601 format, which is YYYY-MM-DD.

```javascript

SELECT 
  payment_id, 
  amount, 
  payment_date 
FROM 
  payment 
WHERE 
  payment_date BETWEEN '2007-02-15' AND '2007-02-20' 
  AND amount > 10 
ORDER BY 
  payment_date;

```


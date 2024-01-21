# BOOLEAN

that can have three values: true, false and NULL.

The following table shows the valid literal values for TRUE and FALSE in PostgreSQL.

| True    | False   |
|:--------| :-------|
| true    | false   |
| 't'     | 'f'     |
| ‘true’  | ‘false’ |
| 'y'     | ‘n’     |
| 'yes'   | ‘no’    |
| '1'     | ‘0’    |

*Example*

```javascript
INSERT INTO stock_availability (product_id, available)
VALUES
	(100, TRUE),
	(200, FALSE),
	(300, 't'),
	(400, '1'),
	(500, 'y'),
	(600, 'yes'),
	(700, 'no'),
	(800, '0');

    SELECT *
FROM stock_availability
WHERE available = 'yes';

 product_id | available
------------+-----------
        100 | t
        300 | t
        400 | t
        500 | t
        600 | t
(5 rows)
```


## Set a default value of the Boolean column

To set a default value for an existing Boolean column, you use the SET DEFAULT clause in the ALTER TABLE statement.

```javascript
ALTER TABLE stock_availability 
ALTER COLUMN available
SET DEFAULT FALSE;
```

If you insert a row without specifying the value for the available column, PostgreSQL uses FALSE:

```javascript
INSERT INTO stock_availability (product_id)
VALUES (900);

SELECT *
FROM stock_availability
WHERE product_id = 900;

 product_id | available
------------+-----------
        900 | f
(1 row)
```



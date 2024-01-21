# NUMERIC

The NUMERIC type can store numbers with a lot of digits.

Syntax:

```javascript
NUMERIC(precision, scale)
```

In this syntax, the precision is the total number of digits and the scale is the number of digits in the fraction part. For example, the number 1234.567 has the precision 7 and scale 3.

If you omit both precision and scale, you can store any precision and scale up to the limit of the precision and scale mentioned above.

In PostgreSQL, the NUMERIC and DECIMAL types are equivalent and both of them are also a part of SQL standard.

If precision is not required, you should not use the NUMERIC type because calculations on NUMERIC values are typically slower than integers, floats, and double precisions.

Example: 

```javascript
DROP TABLE IF EXISTS products;

CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    price NUMERIC(5,2)
);
```

```javascript
INSERT INTO products (name, price)
VALUES ('Phone',500.215), 
       ('Tablet',500.214);
```

```javascript
SELECT * FROM products;
```

Output: 

![output](https://www.postgresqltutorial.com/wp-content/uploads/2017/02/PostgreSQL-NUMERIC-example.png)

## NaN

In addition to holding numeric values, the NUMERIC type can also hold a special value called NaN which stands for not-a-number.

Typically, the NaN is not equal to any number including itself. It means that the expression NaN = NaN returns false.

However, two NaN values are equal and NaN is greater than other numbers. This implementation allows PostgreSQL to sort NUMERIC values and use them in tree-based indexes.


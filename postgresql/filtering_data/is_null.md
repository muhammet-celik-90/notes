# IS NULL

The comparison of NULL with a value will always result in NULL. Additionally, NULL is not equal to NULL so the following expression returns NULL:

```javascript
SELECT null = null AS result;
```

Output:

```javascript
 result
--------
 null
(1 row)
```

## IS NULL

To check if a value is NULL or not, you cannot use the equal to (=) or not equal to (<>) operators. Instead, you use the IS NULL operator.

Syntax:

```javascript
value IS NULL
```

The IS NULL operator returns NULL if the value is NULL or false otherwise.

To negate the IS NULL operator, you use the IS NOT NULL operator.


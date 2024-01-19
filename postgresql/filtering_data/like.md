# LIKE

Suppose that you want to find customers, but you don’t remember their names exactly. However, you can recall that their names begin with something like Jen.

How do you locate the exact customer from the database? You can identify customers in the  customer table by examining the first name column to see if any values begin with Jen. However, this process can be time-consuming, especially when the customer table has a large number of rows.

Fortunately, you can use the PostgreSQL LIKE operator to match the first names of customers with a string using the following query:

```javascript
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name LIKE 'Jen%';
```

Output:
```javascript
 first_name | last_name
------------+-----------
 Jennifer   | Davis
 Jennie     | Terry
 Jenny      | Castro
(3 rows)
```

PostgreSQL offers two wildcards:

Percent sign ( %) matches any sequence of **zero** or **more characters**.
Underscore sign (_)  matches any **single character**.

If the pattern does not contain any wildcard character, the LIKE operator behaves like the equal (=) operator.

### LIKE operator a pattern that contains both wildcards

```javascript
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name LIKE '_her%' 
ORDER BY 
  first_name;
```

```javascript
 first_name | last_name
------------+-----------
 Cheryl     | Murphy
 Sherri     | Rhodes
 Sherry     | Marshall
 Theresa    | Watson
(4 rows)
```

## NOT LIKE

```javascript
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name NOT LIKE 'Jen%' 
ORDER BY 
  first_name;
```

Output: 

```javascript
 first_name  |  last_name
-------------+--------------
 Aaron       | Selby
 Adam        | Gooch
 Adrian      | Clary
 Agnes       | Bishop
...
```

## PostgreSQL extensions of the LIKE operator

PostgreSQL ILIKE operator, which is similar to the LIKE operator, enables **case-insensitive** matching. For example:

```javascript
SELECT 
  first_name, 
  last_name 
FROM 
  customer 
WHERE 
  first_name ILIKE 'BAR%';
```

Output:

```javascript
 first_name | last_name
------------+-----------
 Barbara    | Jones
 Barry      | Lovelace
(2 rows)
```

## LIKE operator with ESCAPE option

Sometimes, the data, that you want to match, contains the wildcard characters % and _

Syntax:
````javascript
string LIKE pattern ESCAPE escape_character;
```

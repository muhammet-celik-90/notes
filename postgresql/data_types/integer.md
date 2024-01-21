# INTEGER

To store the whole numbers in PostgreSQL, you use one of the following integer types: SMALLINT, INTEGER, and BIGINT.

| Name        | Storage Size | Min                        | Max                                   |
|:------------|:-------------|:---------------------------|:--------------------------------------|
| SMALLINT    | 2 bytes      | -32,768                    | +32,767                               |
| INTEGER     | 4 bytes      | -2,147,483,648             | +2,147,483,647                        |
| BIGINT      | 8 bytes      | -9,223,372,036,854,775,808 | +9,223,372,036,854,775,807            |


If you try to store a value outside of the permitted range, PostgreSQL will issue an error.

Unlike MySQL integer, PostgreSQL does not provide unsigned integer types.

## SMALLINT

```javascript
CREATE TABLE books (
    book_id SERIAL PRIMARY KEY,
    title VARCHAR (255) NOT NULL,
    pages SMALLINT NOT NULL CHECK (pages > 0)
);

```

In this example, the pages column is a SMALLINT column. Because the number of pages of a book must be positive, we added a CHECK constraint to enforce this rule.


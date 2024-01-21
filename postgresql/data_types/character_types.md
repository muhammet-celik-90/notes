# Character Types: CHAR, VARCHAR, and TEXT

| Character Types                   | Description                         |
|:----------------------------------|:------------------------------------|
|CHARACTER VARYING(n), VARCHAR(n)   |variable-length with length limit    |
|CHARACTER(n), CHAR(n)              |fixed-length, blank padded           |
|TEXT, VARCHAR                      |variable unlimited length            |

Both CHAR(n) and VARCHAR(n)can store up to n characters. If you try to store a string that has more than n characters, PostgreSQL will issue an error.

However, one exception is that if the excessive characters are all spaces, PostgreSQL truncates the spaces to the maximum length (n) and stores the characters.

 If you do not specify the n integer for the VARCHAR data type, it behaves like the TEXT datatype. The performance of the VARCHAR (without the size n) and TEXT are the same.

 Different from other database systems, in PostgreSQL, there is no performance difference among the three character types.

 In most cases, you should use TEXTor VARCHAR. And you use the VARCHAR(n) when you want PostgreSQL to check for the length.

 
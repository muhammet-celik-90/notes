# PostgreSQL SELECT

The SELECT statement has the following clauses:

- `DISTINCT` -> selecting distinct rows (*farklı satırları seçin*)
- `ORDER BY` -> sort rows (*satırları sıralayın*)
- `WHERE`    -> filterin rows (*satırları filtreleyin*)
- `LIMIT` or `FETCH` -> select a subset of rows (*satırların bir alt kümesini seçin*)
- `GROUP BY` -> group rows into group (*satırları gruplar halinde gruplayın*)
- `HAVING`   -> filter groups (*grupları filtreleyin*)
- join with other tables (*diğer tablolara katılma*);
    * `INNER JOIN`
    * `LEFT JOIN`
    * `FULL OUTER JOIN`
    * `CROSS`
    * `JOIN`

- perform set operations (*işlemleri gerçekleştirin*);
    * `UNION`
    * `INTERSECT`
    * `EXCEPT`


## SELECT

```javascript

SELECT
   select_list
FROM
   table_name;

```

- If you specify a list of columns, you need to place a comma (,) between two columns to separate them.
 (*Eğer birden fazla sütundan veri çekecekseniz, sütunların birbirinden virgül (,) ile ayırınız*)

 - If you want to select data from all the columns of the table, you can use an asterisk (*) shorthand instead of specifying all the column names. 
 (*Eğer tablodaki tüm sütunlardan veri çekecekseniz, kısayol olarak yıldız (*) *işaretini kullanabilirsiniz.*)

 - The `FROM` clause is optional. (*`FROM` sözcüğü opsiyoneldir. Herhangi bir tablo adı belirtilmeyecekse silinebilir.*)

 > SQL keywords are case-insensitive. It means that `SELECT` is equivalent to `select` or `Select`. (*`SELECT` sözcüğü büyük-küçük harfe duyarlı değildir. `select` ya da `Select` sözcüğü aynı anlama gelir*)

 > It is a good practice to explicitly specify the column names in the `SELECT` clause whenever possible to get only necessary data from the database. And you should only use the asterisk (*)* shorthand for the ad-hoc queries that examine data from the database. (*`SELECT` ifadesinden sonra sütun ismi kullanarak verileri çekmek güzel bir yöntemdir. Böylece veritabanını gereksiz yormamış, verileri hızlı çekmiş oluruz. Sadece geçici olarak veritabanındaki verileri incelem istediğimiz zaman asteriks (*) *işaretini kullanmalıyız.*)


### CONCATENATION OPERATOR  ||


 ```javascript
 
 SELECT 
   first_name || ' ' || last_name,
   email
FROM 
   customer;
 
 ```

 In this example, we used the **concatenation operator ||** to concatenate the first name, space, and last name of every customer. (Bu ifade, **birleştirme operatörü ||** ile sütunları nasıl birleştireceğimizin bir örneğidir.)



## Column Alias


Column aliases is used for assiging temporary names to columns in queries. (*Sütun isimlendirmeyi geçici olarak sütunlara isim vermek için kullanırız.*)

```javascript

SELECT column_name AS alias_name
FROM table_name;

```

We assigned to alias_name to column_name with AS keyword. AS keyword is optional, we can omit it. (*AS anahtar sözcüğünü kullanarak alias_name ismini column_name sütununun ismine atadık. Buradaki AS anahtar sözcüğü opsiyoneldir. İstersek kullanmayabiliriz.*)

```javascript

SELECT column_name alias_name
FROM table_name;

```


###  Column aliases that contain spaces

If a column alias contains one or more spaces, you need to surround it with double quotes. (*Eğer takma isimde boşluk ve daha fazla bir şeyler kullanmak istersek, takma adı tırnak işareti ile çevrelemeliyiz*)

```javascript

column_name AS "column alias"

```


### Database creation and use: 
```mysql
CREATE DATABASE test;
USE test;

```
### Create Table:
```mysql
CREATE TABLE mytable (
  id INT NOT NULL AUTO_INCREMENT,
  col1 INT NOT NULL DEFAULT 1,
  col2 VARCHAR(45) NULL,
  col3 DATE NULL,
  PRIMARY KEY (`id`));
```
### Insert

> Normal Insertion
```mysql
INSERT INTO mytable(col1, col2)
VALUES(val1, val2);

```
> Insert the retrieved data 
```mysql
INSERT INTO mytable1(col1, col2)
SELECT col1, col2
FROM mytable2;
```

> Insert the contents of a table into a new table 
```sql
CREATE TABLE newtable AS
SELECT * FROM mytable;
```
### modify the table 
 
> Add column
```sql
ALTER TABLE mytable
ADD col CHAR(20);

```
> Delete Column
```sql
ALTER TABLE mytable
DROP COLUMN col;

```
> Delete Table
```sql
DROP TABLE mytable;
```

### Update
```sql
UPDATE mytable
SET col = val
WHERE id = 1;

```

### Delete
```sql
DELETE FROM mytable
WHERE id = 1;

```

> TRUNCATE TABLE can empty the table, that is, delete all rows. 
```sql
TRUNCATE TABLE mytable;
```

>> When using update and delete operations, you must use the WHERE clause, otherwise the data in the entire table will be destroyed. You can use the SELECT statement to test first to prevent mistaken deletion.

### Queries

### Distinct
>The same value will only appear once. It acts on all columns, which means that the values ​​of all columns are the same to be considered the same.

```sql
SELECT DISTINCT col1, col2
FROM mytable;
```
### Limit
> Limit the number of rows returned. There can be two parameters, the first parameter is the starting row, starting from 0; the second parameter is the total number of rows returned. 
> Return to the first 4 rows:

```sql
SELECT *
FROM mytable
LIMIT 4;

```

```sql
SELECT *
FROM mytable
LIMIT 0, 4;

```
> return lines 3~5
```sql
SELECT *
FROM mytable
LIMIT 2, 3;

```
### Sort

###     ASC : Ascending order (default)
###    DESC : descending order 

> You can sort by multiple columns, and specify a different sorting method for each column: 
```sql
SELECT *
FROM mytable
ORDER BY col1 DESC, col2 ASC;
```

### Filter
> The data that is not filtered is very large, resulting in excess data being transmitted through the network, thus wasting network bandwidth. Therefore, try to use SQL statements to filter unnecessary data, instead of transmitting all the data to the client and then filtering by the client.

```sql
SELECT *
FROM mytable
WHERE col IS NULL;

```

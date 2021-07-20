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

. Normal Insertion
```mysql
INSERT INTO mytable(col1, col2)
VALUES(val1, val2);

```
. Insert the retrieved data 
```mysql
INSERT INTO mytable1(col1, col2)
SELECT col1, col2
FROM mytable2;
```

. Insert the contents of a table into a new table 
```sql
CREATE TABLE newtable AS
SELECT * FROM mytable;
```
### modify the table 
 
. Add column
```sql
ALTER TABLE mytable
ADD col CHAR(20);

```
.Delete Column
```sql
ALTER TABLE mytable
DROP COLUMN col;

```

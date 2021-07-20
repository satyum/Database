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

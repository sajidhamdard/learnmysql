## MySQL Commands

### Create Database

```
create database wecodeacademy;
```

### Show Databases

```
show databases;
```

### Select Database

```
use wecodeacademy;
```

### Create Table

```
CREATE TABLE `student` ( 
 `studentid` int(10) UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `name` varchar(255) , 
 `email_address` varchar(255), 
 `city` varchar(255) , 
 `fathername` varchar(255),
 `mobile` int(15)
);
```

### Show Tables

```
show tables;
```

### Select All Columns from a table

```
select * from student;
```

### Select specific columns from a table

```
select name, mobile from student;
```

### Insert into table using column names

```
INSERT INTO student (name, email_address, city, fathername, mobile) VALUES ('Shera' ,'sher.badnam@gmail.com', 'Merta', 'Kalam Khan',  999999999);
```

### Insert into table without using column names

```
INSERT INTO student VALUES (1, 'Shera' ,'sher.badnam@gmail.com', 'Merta', 'Kalam Khan',  999999999);
```

### Where Condition examples

```
select * from student where name  = 'Sajid' or studentid  = 2;
```

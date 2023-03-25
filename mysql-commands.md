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

select * from student where name  = 'Sajid' and studentid  = 2;
```

### distinct

```
select distinct name from student;
```

```
select count(*) from student;

select * from student where fathername is null;

select * from student where fathername is not null;

select * from student where studentid <> 5;

select * from student where studentid < 5;

select * from student where studentid > 5;

select * from student where studentid >= 5;

select * from student where studentid <= 5;

select * from student where studentid in (1,4,7,8,10);

select * from student where studentid not in (1,2,3);

select * from student where email_address like '%sher';

select * from student where email_address like '%er%';

select * from student where email_address like '%gmail.com';

select * from student where email_address like '%badnam%.com';

select * from student where studentid between 5 and 8;

select * from student order by name;

select * from student order by name asc;

select * from student order by name desc;

select * from student where not studentid = 2;

SET SQL_SAFE_UPDATES=0;

delete from student where Name = 'Shera';

delete from student;

drop table student;

drop database wecodeacademy;

select min(studentid) from student;

select max(name) from student;

select count(*) from student;

select count(studentid) from student;

select count(*) from student where fathername = 'Kalam Khan';

select avg(studentid) from student where fathername = 'Kalam Khan';

select sum(studentid) from student;
```

# MySQL_Commands

### 1.Create Database.

Es command ka use DBMS me database create karane ke liye kiya jata hai.
~~~
CREATE DATABASE database_name;
~~~


### 2.Show Databases.

Es command ka use DBMS me jitane bhi database hai onhe dikhan ke liye hota hai.
~~~
SHOW DATABASES;
~~~

### 3. Use Database.

Es command ka use database ko use karane ke liye hota hai.
~~~
USE Database_name;
~~~

### 4. Create Table.

Es command ka use database me table create karane ke liye hota hai.
~~~
CREATE TABLE Table_name (
Column1 DATATYPE CONTRAINT,
Column2 DATATYPE CONTRAINT,
...
);
~~~

### 5.Alter Table.

- #### Add column in table.

Es command ka use table me column add karane ke liye kiya jata hai.
~~~
ALTER TABLE table_name ADD column_name DATATYPE;
~~~

- #### Add column in table specific position.

Es command ka use table me specific column se pahal column add karane ke liye kiya jata hai.
~~~
ALTER TABLE table_name ADD current_column_name AFTER new_cloumn_name;
~~~

- #### Modify column in table.

Es commad ka use table column ko modify karane ke liye kiya jata hai.
~~~
ALTER TABLE table_name MODIFY column_name DATATYPE;
~~~

- #### Rename column in table.

Es command ka use table ke  column ke name ko change karane ke liye kiya jata hai.
~~~
ALTER TABLE table_name RENAME current_column_name TO new_column_name;
~~~

- #### Drop column in table.

Es command ka use table me column ko delete karane ke liye kiya jata hai.
~~~
ALTER TABLE table_name DROP column_name;
~~~

### 6. Insert data in table.

- #### Insert data in table with column name.

Es command ka use table me column name ke sath data insert karane ke liye kiya jata hai.
~~~
INSERT INTO table_name (Column1,Column2,Column3, ...)
VALUES (Value1,Value2,Value3,...);
~~~

- #### Insert data in table without column name.

Es cammand ka use table me bina column name ka use kiye data insert karane ke liye kiya jata hai.lakin esme column name ka order pata hona chahiye.
~~~
INSERT INTO table_name VALUES(Value1,Value2,Value3,...);
~~~

### 7.Delete database in DBMS.

Es command ka use DBMS se database ko drop karane ke liye hota hai.
~~~
DROP database_name;
~~~

### 8.Delete table in database.

Es command ka use database me se table drop karane ke liye hota hai.
~~~
DROP table_name;
~~~

### 9.Select data from table.

- #### Get full record in table.

Es command ka use table me se sare column ka data get karane ke liye hota hai.
~~~
SELECT * FROM table_name;
~~~

- #### Get specific column record in table.

Es command ka use table me se specific column ka data get karane ke liye kiya jata hai.
~~~
SELECT Column_name1, Column_name2 FROM table_name;
~~~

### 10.Select data from table with condition.

- #### Single condition.

Es command ka use table me se specific condition ke sath data get karane ke liye kiya jata hai.
~~~
SELECT * FROM table_name WHERE condition;
~~~

- #### Multiple condition.

Es command ka use table me se multiple condition ke sath data get karane ke liye kiya jata hai.

~~~
SELECT * FROM table_name WHERE condition AND condition;

SELECT * FROM table_name WHERE condition OR condition;

SELECT * FROM table_name WHERE condition NOT condition;
~~~

### 11.Select unique data from table.

Es command ka use table me se unique data get karane ke liye kiya jata hai.
~~~
SELECT DICTINCT * FROM table_name;
~~~

### 12.Update data in table.

- #### Single column update in table.

Es command ka use table me single column ko update karane ke liye kiya jata hai.
~~~
UPDATE table_name SET column_name = 'Update value' WHERE condtion;
~~~

- #### Multiple column update in table.

Es command ka use table me multiple column ko update karane ke liye kiya jata hai.
~~~
UPDATE table_name SET column_name = 'Update value', column_name = 'Update value' WHERE conditionl
~~~ 

### 13.Delete data in table.

- #### Delete all data in table.

Es command ka use table me se all record ko delete karane ke liye kiya jata hai.
~~~
DELETE FROM table_name;
~~~

- #### Delete specific data in table.

Es command ka use table me se particular record ko delete karane ke liye kiya jata hai.
~~~
DELETE FROM table_name WHERE condition;
~~~

### 14.Get limit data in table.

Es command ka use table me se limit data get karane ke liye liya jata hai.
~~~
SELECT * FROM LIMIT number_of_limit;
~~~

### 15.temporary column name change.

Es command ka use table ka data get karate time particular column ka name change karane ke liye hota hai.
~~~
SELECT column_name AS temporary_name FROM table_name;
~~~

### 16.Get group by data in table.

Es cammand ka use yeh dekhane ke liye kiya jata hai. ki particular value ke sath kitane record table me fill hai.

- #### Get group by data specific column in table.

Es command use table me se specific column name ke sath data ko group by get karane k liye kiya jata hai.
~~~
SELECT column_name1 FROM table_name GROUP BY column_name1;
~~~

- #### Get group by data with particular condition in table.

Es command ka use table me se specific condition ke sath data ko group by get karane ke liye kiya jata hai.
~~~
SELECT column_name FROM table_name WHERE condition GROUP BY column_name;
~~~

### 17.Get order by data in table.

- #### Get data by ascending order in table.

Es command ka use table me se ascending order me data get karane ke kiye kiya jata hai.
~~~
SELECT * FROM table_name ORDER BY column_name;

SELECT * FROM table_name ORDER BY column_name ASC;
~~~

- #### Get data by descending order in table.

Es command ka use table me se descending order me data get karane ke liye kiya jata hai.
~~~
SELECT * FROM table_name ORDER BY column_name DESC;
~~~

### 18.Having in table.

Es command ka use yhe dekhane ke liye kiya jata hai. ki particular value ke sath koi data table me fill hai ya nhi.
~~~
SELECT * FROM table_name HAVING condition;
~~~


### 19.Insert data into a table using data from another table.

Es command ka use another table ka data kisi or table me insert katane ke liye hota hai.lakin esme table1 or table2 ke column order same hone chahiye. 

- #### Insert all data.
~~~
INSERT INTO table_name1 SELECT * FROM table_name2;
~~~

- #### Insert data with particular condition;

~~~
INSERT INTO table_name1 SELECT * FROM table_name2 WHERE codition;
~~~

- #### Insert data specific column with particular condition.

~~~
INSERT INTO table_name1(column1,column2,...) SELECT * FROM table_name2 WHERE condition.
~~~

### 20.Case in table.

Es command ka use table me se data get karte time particular statement ke sath data dekhane ke liye kiya jata hai.

~~~
SELECT column1,column2, ...
CASE 
   WHEN condition THEN statement
   ...
   ELSE statement
END AS temporary_column_name FROM table_name;
~~~   





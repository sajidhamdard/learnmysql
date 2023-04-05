# MySQL_Commands

### 1.Create Database.

Es command ka use DBMS me database create karane ke liye kiya jata hai.
~~~
CREATE DATABASE wecode_academy;
~~~

### 2.Show Databases.

Es command ka use DBMS me jitane bhi database hai onhe show karane ke liye hota hai.
~~~
SHOW DATABASES;
~~~

### 3. Use Database.

Es command ka use database ko use karane ke liye hota hai.
~~~
USE wecode_academy;
~~~

### 4. Create Table.

Es command ka use database me table create karane ke liye hota hai.
- **studentId** Column_name hai jisko humne  **INTEGER** datatype di hai eska matlab hai ki es column me sirf number datatype ki value jaygi. **UNSIGNED** ka matlab hai ki yhe negative me number nhi laga. **PRIMARY KEY** ka matlab hai ki record ko uniquely identify karega. **NOT NULL** ka matlab hai ki es column ki value null nhi ho sakti.
**AUTO_INCREMENT** ka matlab hai ki **PRIMARY KEY** automatic increment hoti rahagi.
 
~~~
CREATE TABLE students(
studentId INTEGER UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT,
studentName VARCHAR(155) NOT NULL,
fatherName VARCHAR(155) NOT NULL,
mobileNumber BIGINT NOT NULL,
country VARCHAR(155) NOT NULL,
state VARCHAR(155) NOT NULL,
city VARCHAR(155) NOT NULL,
pincode INTEGER NOT NULL
);
~~~

### 5.Alter Table.

- #### Add column in table.

Es command ka use table me column add karane ke liye kiya jata hai.
~~~
ALTER TABLE students ADD age INTEGER;
~~~

- #### Add column in table specific position.

Es command ka use table me specific column se pahal column add karane ke liye kiya jata hai.
~~~
ALTER TABLE students ADD COLUMN Age INTEGER AFTER City;
~~~

- #### Modify column in table.

Es commad ka use table column ko modify karane ke liye kiya jata hai.
~~~
ALTER TABLE students MODIFY COLUMN Age INTEGER;
~~~

- #### Rename column in table.

Es command ka use table ke  column ke name ko change karane ke liye kiya jata hai.
~~~
ALTER TABLE table_name RENAME COLUMN City TO myCity;
~~~

- #### Drop column in table.

Es command ka use table me se column ko delete karane ke liye kiya jata hai.
~~~
ALTER TABLE students DROP COLUMN City;
~~~

### 6. Insert data in table.

- #### Insert data in table with column name.

Es command ka use table me column name ke sath data insert karane ke liye kiya jata hai.
~~~
INSERT INTO table_name (studentName,fatherName,mobileNumber, ...)
VALUES ('wecode academy','academy',1234567899,...);
~~~

- #### Insert data in table without column name.

Es cammand ka use table me bina column name ka use kiye data insert karane ke liye kiya jata hai.lakin esme column name ka order pata hona chahiye.
~~~
INSERT INTO table_name VALUES('wecode academy','academy',1234567899,...);
~~~

### 7.Delete database in DBMS.

Es command ka use DBMS se database ko drop karane ke liye hota hai.
~~~
DROP wecode_academy;
~~~

### 8.Delete table in database.

Es command ka use database me se table drop karane ke liye hota hai.
~~~
DROP students;
~~~

### 9.Select data from table.

- #### Get full record in table.

Es command ka use table me se sare column ka data get karane ke liye hota hai.
~~~
SELECT * FROM students;
~~~

- #### Get specific column record in table.

Es command ka use table me se specific column ka data get karane ke liye kiya jata hai.
~~~
SELECT studentName, fatherName, mobileNumber FROM students;
~~~

### 10.Select data from table with condition.

- #### Single condition.

Es command ka use table me se specific condition ke sath data get karane ke liye kiya jata hai.
~~~
SELECT * FROM students WHERE studentId = 1;
~~~

- #### Multiple condition.

Es command ka use table me se multiple condition ke sath data get karane ke liye kiya jata hai.

~~~
SELECT * FROM students WHERE studentId = 1 AND studentName = 'wecode';

SELECT * FROM students WHERE studentId = 4 OR fatherName = 'academy';

SELECT * FROM students WHERE studentId = 3 NOT mobileNumber = 343243242;
~~~

### 11.Select unique data from table.

Es command ka use table me se unique data get karane ke liye kiya jata hai.
~~~
SELECT DICTINCT * FROM students;
~~~

### 12.Update data in table.

- #### Single column update in table.

Es command ka use table me single column ko update karane ke liye kiya jata hai.
~~~
UPDATE students SET studentName = 'wecode academy' WHERE studentId = 3;
~~~

- #### Multiple column update in table.

Es command ka use table me multiple column ko update karane ke liye kiya jata hai.
~~~
UPDATE students SET studentName = 'wecode academy', mobileNumber = 1234567 WHERE studentId = 3;
~~~ 

### 13.Delete data in table.

- #### Delete all data in table.

Es command ka use table me se all record ko delete karane ke liye kiya jata hai.
~~~
DELETE FROM students;
~~~

- #### Delete specific data in table.

Es command ka use table me se particular record ko delete karane ke liye kiya jata hai.
~~~
DELETE FROM students WHERE studentId = 1;
~~~

### 14.Get limit data in table.

Es command ka use table me se limit data get karane ke liye liya jata hai.
~~~
SELECT * FROM students LIMIT 2;
~~~

### 15.temporary column name change.

Es command ka use table ka data get karate time particular column ka name change karane ke liye hota hai.
~~~
SELECT studentName AS sName FROM students;
~~~

### 16.Get group by data in table.

Es cammand ka use yeh dekhane ke liye kiya jata hai. ki particular value ke sath kitane record table me fill hai.

- #### Get group by data specific column in table.

Es command use table me se specific column name ke sath data ko group by get karane k liye kiya jata hai.
~~~
SELECT studentName FROM students GROUP BY studentName;
~~~

- #### Get group by data with particular condition in table.

Es command ka use table me se specific condition ke sath data ko group by get karane ke liye kiya jata hai.
~~~
SELECT studentName FROM students WHERE studentId = 2 GROUP BY studentName;
~~~

### 17.Get order by data in table.

- #### Get data by ascending order in table.

Es command ka use table me se ascending order me data get karane ke kiye kiya jata hai.
~~~
SELECT * FROM students ORDER BY mobileNumber;

SELECT * FROM students ORDER BY mobileNumber ASC;
~~~

- #### Get data by descending order in table.

Es command ka use table me se descending order me data get karane ke liye kiya jata hai.
~~~
SELECT * FROM students ORDER BY studentId DESC;
~~~

### 18.Having in table.

Es command ka use yhe dekhane ke liye kiya jata hai. ki particular value ke sath koi data table me fill hai ya nhi.
~~~
SELECT * FROM students HAVING studentName = 'wecode';
~~~


### 19.Insert data into a table using data from another table.

Es command ka use another table ka data kisi or table me insert karane ke liye hota hai.lakin esme table1 or table2 ke column order same hone chahiye. 

- #### Insert all data.
~~~
INSERT INTO students SELECT * FROM students2;
~~~

- #### Insert data with particular condition;

~~~
INSERT INTO students SELECT * FROM students2 WHERE studentId = 3;
~~~

- #### Insert data specific column with particular condition.

~~~
INSERT INTO students(studentName,fatherName,...) SELECT * FROM students2 WHERE studentId = 5.
~~~

### 20.Case in table.

Es command ka use table me se data get karte time particular statement ke sath data dekhane ke liye kiya jata hai.

~~~
SELECT studentName,marks, ...
CASE 
   WHEN marks > 60 THEN 'Good'
   WHEN marks > 80 THEN 'Very good'
   WHEN marks > 90 THEN 'Excellent'
   ELSE 'fail'
END AS result FROM students;
~~~   





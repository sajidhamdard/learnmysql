# MySQL_Commands

## Create Database.

Es command ka use DBMS me database create karane ke liye kiya jata hai.
~~~
CREATE DATABASE wecode_academy;
~~~

## Show Databases.

Es command ka use DBMS me jitane bhi database hai onhe show karane ke liye hota hai.
~~~
SHOW DATABASES;
~~~

## Use Database.

Es command ka use database ko use karane ke liye hota hai.
~~~
USE wecode_academy;
~~~

### Create Table.

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

## Alter Table.

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

## Insert data in table.

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

## Delete database in DBMS.

Es command ka use DBMS se database ko drop karane ke liye hota hai.
~~~
DROP wecode_academy;
~~~

## Delete table in database.

Es command ka use database me se table drop karane ke liye hota hai.
~~~
DROP students;
~~~

## Select data from table.

- #### Get full record in table.

Es command ka use table me se sare column ka data get karane ke liye hota hai.
~~~
SELECT * FROM students;
~~~

- #### Get specific column record in table.

Es command ka use table me se specific column ka data get karane ke liye kiya jata hai.
~~~
SELECT studentName, fatherName,mobileNumber FROM students;
~~~

## Select data from table with condition.

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

## Select unique data from table.

Es command ka use table me se unique data get karane ke liye kiya jata hai.
~~~
SELECT DICTINCT * FROM students;
~~~

## Update data in table.

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

## Delete data in table.

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

## Get limit data in table.

Es command ka use table me se limit data get karane ke liye liya jata hai.
~~~
SELECT * FROM students LIMIT 2;
~~~

## temporary column name change.

Es command ka use table ka data get karate time particular column ka name change karane ke liye hota hai.
~~~
SELECT studentName AS sName FROM students;
~~~

## Get group by data in table.

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

## Get order by data in table.

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

## Having in table.

Es command ka use yhe dekhane ke liye kiya jata hai. ki particular value ke sath koi data table me fill hai ya nhi.
~~~
SELECT * FROM students HAVING studentName = 'wecode';
~~~

## Insert data into a table using data from another table.

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

## Case in table.

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

## Comments in MySQL.

Comment ka use queri ko explain karane ke liye kiya jata hai.

#### Single line comment.
~~~
-- comment
~~~

#### Multiple line comments
~~~
/* 
comment 
*/
~~~

## Aggregate functions in DBMS.

Aggregate function ka use DBMS me record ko sum,count,avg,max,min karane ke liye hota hai.
 
### Sum function.

- #### Sum function without condition.

Sum function ka use database me se numeric record ka sum karane ke liye hota hai. Without condition se studentFee table me se all month ki fees sum karga.
~~~
SELECT SUM(fees) FROM studentFee;
~~~

- #### Sum function with condition.

Sum function ka use database me se numeric record ka sum karane ke liye hota hai. with condition se studentFee table me se only january month ki fees sum karga.
~~~
SELECT SUM(fees) FROM studentFee WHERE month = 'January';
~~~

### Count function.

- #### Count function without condition.

Count function ka use database me record ka count karane ke liye hota hai.Es queri me all studentId ka count karga.
~~~
SELECT COUNT(studentId) FROM students;
~~~

- #### Count function with condition.

Count function ka use database me record ka count karane ke liye hota hai. Es queri me sirf unhi student ka count hoga jiski age 15 year se badi hai.
~~~
SELECT COUNT(studentId) FROM students WHERE studentAge > 15;
~~~

### Average function.

- #### Average function without condition.

Average function ka use database me se numeric record ka average get karane ke liye hota hai. Es queri me all student ki age ki average nikali jaygi.
~~~
SELECT AVG(age) FROM students;
~~~

- #### Average function with condition.

Average function ka use database me se numeric record ka average get karane ke liye hota hai. Es queri me sirf unhi student ki age ki average nikali jaygi jinka name 'wecode' hai.
~~~
SELECT AVG(age) FROM students WHERE studentName = 'wecode';
~~~

### Max function.

- #### Max function without condition.

Max function ka use database me se numeric record me se maximum value get karane ke liye hota hai. Es queri me student me se kiski age sabse badi hai yhe get ki jaygi.
~~~
SELECT studentName,MAX(age) FROM students GROUP BY studentName LIMIT 1;
~~~ 

- #### Max function with condition.

Max function ka use database me se numeric record me se maximum value get karane ke liye hota hai. Es queri me 'wecode' studentName me se kiski age maximum hai yhe get ki jaygi.
~~~
SELECT studentId,MAX(age) FROM students WHERE studentName = 'wecode' GROUP BY studentId LIMIT 1;
~~~

### Min function.

- #### Min function without condition.

Min function ka use database me se numeric record me se minimum value get karane ke liye hota hai. Es queri me student me se kiski age sabse choti hai yhe get ki jaygi.
~~~
SELECT studentName,MIN(age) FROM students GROUP BY studentName LIMIT 1;
~~~ 

- #### Min function with condition.

Min function ka use database me se numeric record me se minimum value get karane ke liye hota hai. Es queri me 'wecode' studentName me se kiski age minimum hai yhe get ki jaygi.
~~~
SELECT studentId,MIN(age) FROM students WHERE studentName = 'wecode' GROUP BY studentId LIMIT 1;
~~~

## Other function.

- ### Null function.

Null funcrion ka use table me se data get karte time particular column ki null value ki jagah default value set karane ke liye hota hai.
~~~
SELECT studentName,IF NULL(mobileNumber, 9843853847) FROM students;
~~~

## Logical operator in DBMS.

- #### AND operator.

AND operator ka use multiple condition lagane ke liye kiya jata hai. Esme all condition true hone per hi koi queri data return karti hai.
~~~
SELECT * FROM students WHERE studentName = 'wecode' AND studentId = 1;
~~~

- #### OR operator.

OR operator ka use multiple condition lagane ke liye kiya jata hai. Esme koi ek  condition true hone per hi koi queri data return karti hai. Jo condition true hogi oske related data return hoga. ager all condition true hoti hai to onke letated data return hoga.
~~~
SELECT * FROM students WHERE studentName = 'wecode'  OR studentId = 5;
~~~

- #### NOT operator.

NOT operator me jo condition true hoti hai oska data return nhi hota hai. oske alava queri all data return karti hai. Es queri me studentId 5 ka data return nhi hoga.
~~~
SELECT * FROM students WHERE NOT studentId = 5;  
~~~

- #### IN operator.

IN operator ka use multiple condition ko sort me lagane ke liye kiya jata hai. Esme jo condition true hogi queri oska data return karti jaygi.
~~~
SELECT * FROM students WHERE studentId IN (1,2,3,4,5);
~~~

- #### LIKE operator.

LIKE operator ka use asi situation me kiya jata hai jaha hum value ka chota part yad ho or osi value ka data lena ho.

> ##### LIKE with % searchValue.

% se pahal kuch bhi ho sakta hai lakin oske aage searchValue honi chahiye.
~~~
SELECT * FROM students WHERE studentName LIKE '%khan';
~~~

> ##### LIKE with % searchValue %;

% se pahal or % ke bade kuch bhi ho sakta hai. lakin bich me searchValue honi chahiye.
~~~
SELECT * FROM students WHERE studentEmail LIKE '%khan12@gmail%';
~~~

> ##### LIKE with searchValue %

% ke bade kuch bhi ho sakta hai lakin pahal searchValue honi chahiye.
~~~
SELECT * FROM students WHERE mobileNuber LIKE '1234%';
~~~

- #### BETWEEN operator.

BETWEEN operator ka use two condition ke bich ka record get karane ke liye kiya jata hai. 
~~~
SELECT * FROM students WHERE studentId BETWEEN 5 AND 8;
~~~

- #### EXISTS operator.

EXISTS operator ka use table me particular value ke sath koi record fill hai ya nhi yhe dekhane ke liye kiya jaya hai. or particulr value ke sath record fill hota hai to queri table me se all data return karti hai.
~~~
SELECT * FROM students WHERE EXISTS(SELECT * FROM students WHERE studentName = "wecode");
~~~

- #### ALL operator.

All operator ka use table me particular value ke sath koi record fill hai ya nhi yhe dekhane ke liye kiya jaya hai. or record fill hota hai to sub queri jo data retrun karti hai. os main queri se compare karte hai. comparision ke according main queri data return karti hai.
~~~
SELECT * FROM students WHERE studentId >= ALL (SELECT studentId FROM students WHERE fatherName = 'wecode khan');
~~~

- #### ANY operator.

ANY operator ka use table me particular value ke sath koi record fill hai ya nhi yhe dekhane ke liye kiya jaya hai. or record fill hota hai to sub queri jo data retrun karti hai. os main queri se compare karte hai. comparision ke according main queri data return karti hai.
~~~
SELECT * FROM students WHERE studentId <= ANY (SELECT studentId FROM students WHERE studentId > 4);
~~~






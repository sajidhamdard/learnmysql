# MySQL_Commands

## Create Database

Create Database ek database management system (DBMS) mein ek command hai, jiski madad se hum nayi database create kar sakte hai. Create Database command ka upyog DBMS ke databases ko manage karne ke liye kiya jata hai.Jab hum Create Database command ka upyog karte hai, to DBMS nayi database create karta hai, jisme hum tables, views, indexes, aur constraints jaise objects ko create kar sakte hai. 

Syntax :
~~~
create database database_name;
~~~

Example : 
```sql
CREATE DATABASE wecode_academy;
```

## Show Databases.

SHOW DATABASES ek database management system (DBMS) command hai, jiski madad se hum DBMS mein available databases ko dekh sakte hai. Is command ko use karne se pahle, hume DBMS mein logged in hona chahiye.SHOW DATABASES command ka upyog karne se, DBMS mein available databases ka list show hota hai. Ye command information_schema database ke sath sath, user-defined databases ko bhi show karta hai. Is command ke output mein database ke name, aur sometimes other information like database size or owner, display hota hai.

Syntax :
~~~
SHOW DATABASE;
~~~

Example :
```sql
SHOW DATABASES;
```

## Use Database

"Use database" ek SQL statement hai jo database management system (DBMS) mein ek database select karne ke liye use kiya jata hai. Jab hum "Use database" command ka upyog karte hai, to hum ek specific database ko select karte hai, aur us database ke saare tables aur data ko access kare sakta hai.

Syntax :
```
USE database_name;
```

Example :
```sql
USE wecode_academy;
```

### Create Table

Create Table ek database management system (DBMS) mein ek command hai, jiski madad se hum new database table create kar sakte hai. CREATE TABLE statement ka upyog karke, hum table ke columns aur unke data types ko define kar sakte hai.

Yahan par "table_name" ka matlab hai, jo humne create karne wale table ka naam hai. Aur "column1", "column2", "column3" aadi, ka matlab hai jo table mein columns ke naam hai. "datatype" ka matlab hai, ki kis tarah ke data ko column mein store kiya jana hai, jaise ki integer, varchar, date, time, boolean, aadi.

Create Table statement mein columns ke sath-sath hum column ke liye constraints bhi define kar sakte hai, jaise ki UNIQUE, NOT NULL, PRIMARY KEY, aadi. In constraints ke madhyam se hum table ke data ko limit kar sakte hai aur data consistency aur data accuracy ko maintain kar sakte hai.

Syntax :
~~~
CREATE TABLE Table_name (
Column1 DATATYPE CONTRAINT,
Column2 DATATYPE CONTRAINT,
...
);
~~~

- **studentId** Column_name hai jisko humne  **INTEGER** datatype di hai eska matlab hai ki es column me sirf number datatype ki value jaygi. 
- **UNSIGNED** ka matlab hai ki yhe column me  negative number value allow nhi karga.
- **PRIMARY KEY** ka matlab hai ki record ko uniquely identify karega. 
- **NOT NULL** ka matlab hai ki es column ki value null nhi ho sakti.
- **AUTO_INCREMENT** ka matlab hai ki **PRIMARY KEY** automatic increment hoti rahagi.

Example :
```sql
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
```

## Alter Table

Alter Table ek database management system (DBMS) mein ek command hai, jiski madad se hum kisi table mein changes kar sakte hai. Alter Table statement ka upyog table ke schema ya structure ko modify karne ke liye kiya jata hai. Alter Table statement ka upyog table ke columns ko add, modify ya delete karne ke liye bhi kiya ja sakta hai.

- #### Add column in table

Alter Table statement ke dwara hum kisi table mein new column add kar sakte hai.

Syntax :
~~~
ALTER TABLE table_name ADD column_name DATATYPE;
~~~

Example :
```sql
ALTER TABLE students ADD age INTEGER;
```

- #### Add column in table specific position

Es command ka use table me specific column se pahal column add karane ke liye kiya jata hai.

Syntax :
~~~
ALTER TABLE table_name ADD COLUMN current_column_name AFTER new_cloumn_name;
~~~

Example :
```sql
ALTER TABLE students ADD COLUMN Age INTEGER AFTER City;
```

- #### Modify column in table

Alter Table statement ke dwara hum kisi table ke existing column ki data type ya size ko modify kar sakte hai. 

Syntax :
~~~
ALTER TABLE table_name MODIFY COLUMN column_name DATATYPE;
~~~

Example :
```sql
ALTER TABLE students MODIFY COLUMN Age INTEGER;
```

- #### Rename column in table

Alter Table statement ke dwara hum kisi table ke existing column ka naam rename kar sakte hai.

Syntax :
~~~
ALTER TABLE table_name RENAME COLUMN current_column_name TO new_column_name;
~~~

Example :
```sql
ALTER TABLE table_name RENAME COLUMN City TO myCity;
```

- #### Drop column in table

Alter Table statement ke dwara hum kisi table ke existing column ko delete kar sakte hai.

Syntax :
~~~
ALTER TABLE table_name DROP column_name;
~~~

Example :
```sql
ALTER TABLE students DROP COLUMN City;
```

## Insert data in table

Table mein data insert karna database management system (DBMS) mein ek basic operation hai. Jab hum kisi table mein new data insert karte hai, to hum INSERT INTO statement ka upyog karte hai. INSERT INTO statement ka upyog karne se, hum new rows ko table mein insert kar sakte hai.

- #### Insert data in table with column name

Es command ka use table me column name ke sath data insert karane ke liye kiya jata hai.

Syntax :
~~~
INSERT INTO table_name (Column1,Column2,Column3, ...)
VALUES (Value1,Value2,Value3,...);
~~~

Example :
```sql
INSERT INTO table_name (studentName,fatherName,mobileNumber, ...)
VALUES ('wecode academy','academy',1234567899,...);
```

- #### Insert data in table without column name

Es cammand ka use table me bina column name ka use kiye data insert karane ke liye kiya jata hai.lakin esme column name ka order pata hona chahiye.

Syntax :
~~~
INSERT INTO table_name VALUES(Value1,Value2,Value3,...);
~~~

Example :
```sql
INSERT INTO table_name VALUES('wecode academy','academy',1234567899,...);
```

## Delete database in DBMS

DBMS mein 'Delete Database' ka matlab hota hai ki aap database ko puri tarah se mita rahe hain. Jab aap delete database ko select karte hain, toh wo database ke saare tables, indexes, constraints, aur dusre database objects ko permanently delete kar deta hai. Isse puri database ki information remove ho jaati hai aur wapas se restore nahi ki ja sakti. Isliye, Delete Database option ko istemal karne se pahle, aapko puri tarah se sure hona chahiye ki aapko zaroorat nahin hai database ki aur usme rakhi hui information ki.

Syntax :
~~~
DROP database_name;
~~~

Example :
```sql
DROP wecode_academy;
```

## Delete table in database

Delete command ka use database me se table drop karane ke liye hota hai.Jab aap ek table ko delete karte hai, tab uss table ke saare records aur uss table ke saare relationships bhi hamesha ke liye mit jaate hai. Isliye, delete table ka kaam bahut hi important hai aur iska prayog sahi tarah se karna bahut zaroori hai.

Syntax :
~~~
DROP table_name;
~~~

Example :
```sql
DROP students;
```

## Select data from table

Select command ka use kisi database me se data ko select karna ke liye hota hai. Isse hum database me maujood table me se data ko nikal sakte hai. 

- #### Get full record in table

Es command ka use table me se sare column ka data get karane ke liye hota hai.

Syntax :
~~~
SELECT * FROM table_name;
~~~

Example :
```sql
SELECT * FROM students;
```

- #### Get specific column record in table

Es command ka use table me se specific column ka data get karane ke liye kiya jata hai.

Syntax:
~~~
SELECT Column_name1, Column_name2 FROM table_name;
~~~

Example :
```sql
SELECT studentName, fatherName,mobileNumber FROM students;
```

## Select data from table with condition

- #### Single condition

Es command ka use table me se specific condition ke sath data get karane ke liye kiya jata hai.

Syntax :
~~~
SELECT * FROM table_name WHERE condition;
~~~

Example :
```sql
SELECT * FROM students WHERE studentId = 1;
```

- #### Multiple condition

Es command ka use table me se multiple condition ke sath data get karane ke liye kiya jata hai.

Syntax :
~~~
SELECT * FROM table_name WHERE condition AND condition;

SELECT * FROM table_name WHERE condition OR condition;

SELECT * FROM table_name WHERE condition NOT condition;
~~~

Example :
```sql
SELECT * FROM students WHERE studentId = 1 AND studentName = 'wecode';

SELECT * FROM students WHERE studentId = 4 OR fatherName = 'academy';

SELECT * FROM students WHERE studentId = 3 NOT mobileNumber = 343243242;
```

## Select unique data from table

Es command ka use table me se unique data get karane ke liye kiya jata hai.

Syntax :
~~~
SELECT DICTINCT * FROM table_name;
~~~

Example :
```sql
SELECT DICTINCT * FROM students;
```

## Update data in table

DBMS mein "Update" ka matlab hota hai ki hum kisi table ke andar maujood data ko modify kar rahe hote hain. Jab hum kisi record ko update karte hain to uski kuchh values ko change kar diya jaata hai.

- #### Single column update in table

Es command ka use table me single column ko update karane ke liye kiya jata hai.

Syntax :
~~~
UPDATE table_name SET column_name = 'Update value' WHERE condtion;
~~~

Example :
```sql
UPDATE students SET studentName = 'wecode academy' WHERE studentId = 3;
```

- #### Multiple column update in table

Es command ka use table me multiple column ko update karane ke liye kiya jata hai.

Syntax :
~~~
UPDATE table_name SET column_name = 'Update value', column_name = 'Update value' WHERE conditionl
~~~ 

Example :
```sql
UPDATE students SET studentName = 'wecode academy', mobileNumber = 1234567 WHERE studentId = 3;
```

## Delete data in table

Database mein ek table se data delete karne ka matlab hota hai ki aap uss table se kuch records ko hata rahe hain ya table mein se saare record delete kar rahe hain. Iska matlab yeh nahi hai ki aap table ko delete kar rahe hain, sirf uske andar ke data ko delete kar rahe hain.

- #### Delete all data in table

Es command ka use table me se all record ko delete karane ke liye kiya jata hai.

Syntax :
~~~
DELETE FROM table_name;
~~~

Example :
```sql
DELETE FROM students;
```

- #### Delete specific data in table

Es command ka use table me se particular record ko delete karane ke liye kiya jata hai.

Syntax :
~~~
DELETE FROM table_name WHERE condition;
~~~

Example :
```sql
DELETE FROM students WHERE studentId = 1;
```

## Get limit data in table

Es command ka use table me se limit data get karane ke liye liya jata hai.

Syntax :
~~~
SELECT * FROM LIMIT number_of_limit;
~~~

Example :
```sql
SELECT * FROM students LIMIT 2;
```

## Temporary column name change

Es command ka use table ka data get karate time particular column ka name change karane ke liye hota hai.

Syntax :
~~~
SELECT column_name AS temporary_name FROM table_name;
~~~

Example :
```sql
SELECT studentName AS sName FROM students;
```

## Get group by data in table

Group by command ka use table ke data ko kisi column ke basis par group karna hota hai. Isse humara data organized ho jata hai aur hume specific information ko retrieve karne me help milti hai.

- #### Get group by data specific column in table

Es command use table me se specific column name ke sath data ko group by get karane k liye kiya jata hai.

Syntax :
~~~
SELECT column_name1 FROM table_name GROUP BY column_name1;
~~~

Example :
```sql
SELECT studentName FROM students GROUP BY studentName;
```

- #### Get group by data with particular condition in table

Es command ka use table me se specific condition ke sath data ko group by get karane ke liye kiya jata hai.

Syntax :
~~~
SELECT column_name FROM table_name WHERE condition GROUP BY column_name;
~~~

Example :
```sql
SELECT studentName FROM students WHERE studentId = 2 GROUP BY studentName;
```

## Get order by data in table

Order by ka use database me table ke data ko kisi specific column ke basis par arrange karte hain. Isse humein table ke data ko ascending ya descending order mein sort karne ki flexibility milti hai. Jaise ki agar hum kisi product table mein price column ke basis par "order by" karenge toh hum us table ke data ko price ke increasing or decreasing order mein sort kar sakte hain.

- #### Get data by ascending order in table

Es command ka use table me se ascending order me data get karane ke kiye kiya jata hai.

Syntax :
~~~
SELECT * FROM table_name ORDER BY column_name;

SELECT * FROM table_name ORDER BY column_name ASC;
~~~

Example :
```sql
SELECT * FROM students ORDER BY mobileNumber;

SELECT * FROM students ORDER BY mobileNumber ASC;
```

- #### Get data by descending order in table

Es command ka use table me se descending order me data get karane ke liye kiya jata hai.

Syntax :
~~~
SELECT * FROM table_name ORDER BY column_name DESC;
~~~

Example :
```sql
SELECT * FROM students ORDER BY studentId DESC;
```

## Having in table

Having ek database mein table ke upar ek filter lagane ka ek clause hai. Iska upyog tab kiya jata hai jab hamein kisi particular condition ke according grouping kiya hua data chahiye hota hai. Is clause ka upyog osi query mein kiya jata hai jismein GROUP BY clause bhi hota hai.

Syntax :
~~~
SELECT * FROM table_name HAVING condition;
~~~

Example :
```sql
SELECT * FROM students HAVING studentName = 'wecode';
```

## Insert data into a table using data from another table

Es command ka use ek table ka data kisi or table me insert karane ke liye hota hai.lakin esme table1 or table2 ke column order same hone chahiye. 

- #### Insert all data

Syntax :
~~~
INSERT INTO table_name1 SELECT * FROM table_name2;
~~~

Example :
```sql
INSERT INTO students SELECT * FROM students2;
```

- #### Insert data with particular condition

Syntax :
~~~
INSERT INTO table_name1 SELECT * FROM table_name2 WHERE codition;
~~~

Example :
```sql
INSERT INTO students SELECT * FROM students2 WHERE studentId = 3;
```

- #### Insert data specific column with particular condition

Syntax :
~~~
INSERT INTO table_name1(column1,column2,...) SELECT * FROM table_name2 WHERE condition.
~~~

Example :
```sql
INSERT INTO students(studentName,fatherName,...) SELECT * FROM students2 WHERE studentId = 5.
```

## Case in table

Case command ka use table me se data get karte time particular statement ke sath data show ke liye kiya jata hai.

Syntax :
~~~
SELECT column1,column2, ...
CASE 
   WHEN condition THEN statement
   ...
   ELSE statement
END AS temporary_column_name FROM table_name;
~~~   

Example :
```sql
SELECT studentName,marks,
CASE 
   WHEN marks > 60 THEN 'Good'
   WHEN marks > 80 THEN 'Very good'
   WHEN marks > 90 THEN 'Excellent'
   ELSE 'fail'
END AS result FROM students;
```   

## Comments in MySQL

Comment ka use queri ko explain karane ke liye kiya jata hai.

#### Single line comment
Syntax :
~~~
-- comment
~~~

Example :
```sql
-- This query creates the table
```

#### Multiple line comments

Syntax :
~~~
/* 
comment 
*/
~~~

Example :
```sql
/*
This query creates 
the table
*/
```

## Aggregate functions in DBMS

Aggregate functions DBMS mein aise functions hote hai jo table ke data ki summary provide karte hai. In functions ki madad se hum ek column ya fir multiple columns ke data ko combine kar ke summarize kar sakte hai.
 
### Sum function

- #### Sum function without condition.

Sum function ka use database me se numeric record ka sum karane ke liye hota hai. Without condition se studentFee table me se all month ki fees sum karga.

Syntax :
~~~
SELECT aggregate_function_name(column_name) FROM table_name;
~~~

Example :
```sql
SELECT SUM(fees) FROM studentFee;
```

- #### Sum function with condition

Sum function ka use database me se numeric record ka sum karane ke liye hota hai. with condition se studentFee table me se only january month ki fees sum karga.

Syntax :
~~~
SELECT aggregate_function_name(column_name) FROM table_name WHERE condition;
~~~

Example :
```sql
SELECT SUM(fees) FROM studentFee WHERE month = 'January';
```

### Count function

Count function use data ki total count nikalne ke liye hota hai. Isme hum ek specific column ka count nikal sakte hai ya fir saare columns ka count nikal sakte hai.

- #### Count function without condition

Count function ka use database me record ka count karane ke liye hota hai.Es queri me all studentId ka count karga.

Syntax :
~~~
SELECT aggregate_function_name(column_name) FROM table_name;
~~~

Example :
```sql
SELECT COUNT(studentId) FROM students;
```

- #### Count function with condition

Count function ka use database me record ka count karane ke liye hota hai. Es queri me sirf unhi student ka count hoga jiski age 15 year se badi hai.

Syntax :
~~~
SELECT aggregate_function_name(column_name) FROM table_name  WHERE condition;
~~~

Example :
```sql
SELECT COUNT(studentId) FROM students WHERE studentAge > 15;
```

### Average function

- #### Average function without condition

Average function ka use database me se numeric record ka average get karane ke liye hota hai. Es queri me all student ki age ki average nikali jaygi.

Syntax :
~~~
SELECT aggregate_function_name(column_name) FROM table_name;
~~~

Example :
```sql
SELECT AVG(age) FROM students;
```

- #### Average function with condition

Average function ka use database me se numeric record ka average get karane ke liye hota hai. Es queri me sirf unhi student ki age ki average nikali jaygi jinka name 'wecode' hai.

Syntax :
~~~
SELECT aggregate_function_name(column_name) FROM table_name WHERE condition;
~~~

Example :
```sql
SELECT AVG(age) FROM students WHERE studentName = 'wecode';
```

### Max function

- #### Max function without condition

Max function ka use database me se numeric record me se maximum value get karane ke liye hota hai. Es queri me student me se kiski age sabse badi hai yhe get ki jaygi.

Syntax :
~~~
SELECT column_name, aggregate_function_name(column_name) FROM table_name GROUP BY column_name LIMIT number_of_limit;
~~~

Example :
```sql
SELECT studentName,MAX(age) FROM students GROUP BY studentName LIMIT 1;
```

- #### Max function with condition

Max function ka use database me se numeric record me se maximum value get karane ke liye hota hai. Es queri me 'wecode' studentName me se kiski age maximum hai yhe get ki jaygi.

Syntax :
~~~
SELECT column_name, aggregate_function_name(column_name) FROM table_name WHERE condition GROUP BY column_name LIMIT number_of_limit;
~~~

Example :
```sql
SELECT studentId,MAX(age) FROM students WHERE studentName = 'wecode' GROUP BY studentId LIMIT 1;
```

### Min function

- #### Min function without condition

Min function ka use database me se numeric record me se minimum value get karane ke liye hota hai. Es queri me student me se kiski age sabse choti hai yhe get ki jaygi.

Syntax :
~~~
SELECT column_name, aggregate_function_name(column_name) FROM table_name GROUP BY column_name LIMIT number_of_number;
~~~

Example :
```sql
SELECT studentName,MIN(age) FROM students GROUP BY studentName LIMIT 1;
```

- #### Min function with condition

Min function ka use database me se numeric record me se minimum value get karane ke liye hota hai. Es queri me 'wecode' studentName me se kiski age minimum hai yhe get ki jaygi.

Syntax:
~~~
SELECT column_name, aggregate_function_name(column_name) FROM table_name WHERE condition GROUP BY column_name LIMIT nubmer_of_limit;
~~~

Example :
```sql
SELECT studentId,MIN(age) FROM students WHERE studentName = 'wecode' GROUP BY studentId LIMIT 1;
```

## Other function

- ### IFNull function

IFNULL function DBMS mein ek bahut hi upyogi function hai. Iska istemal tab kiya jaata hai jab humein kisi column ki value ko check karna hai ki woh null hai ya nahi. Agar column ki value null hai toh hum IFNULL function ka istemal karke uss column me default value set kar sakte hain.

Syntax :
~~~
SELECT column_name, function_name(column_name, value) FROM  table_name;
~~~

Example :
```sql
SELECT studentName,IF NULL(mobileNumber, 9843853847) FROM students;
```

## Logical operator in DBMS

Logical operators ka use DBMS me queries ko complex aur advanced bana ne ke liyebhoya hai.

- #### AND operator

AND operator ka use multiple condition lagane ke liye kiya jata hai. Esme all condition true hone per hi koi queri data return karti hai.

Syntax :
~~~
SELECT * FROM table_name WHERE condition AND condition;
~~~

Example :
```sql
SELECT * FROM students WHERE studentName = 'wecode' AND studentId = 1;
```

- #### OR operator

OR operator ka use multiple condition lagane ke liye kiya jata hai. Esme koi ek  condition true hone per hi koi queri data return karti hai. Jo condition true hogi oske related data return hoga. ager all condition true hoti hai to onke letated data return hoga.

Syntax :
~~~
SELECT * FROM table_name WHERE condition OR condition;
~~~

Example :
```sql
SELECT * FROM students WHERE studentName = 'wecode'  OR studentId = 5;
```

- #### NOT operator

NOT operator me jo condition true hoti hai oska data return nhi hota hai. oske alava queri all data return karti hai. Es queri me studentId 5 ka data return nhi hoga.

Syntax :
~~~
SELECT * FROM table_name WHERE NOT condition;
~~~

Example :
```sql
SELECT * FROM students WHERE NOT studentId = 5;  
```

- #### IN operator

IN operator DBMS mein ek prakaar ka comparison operator hai jismein hum ek list of values ya phir ek subquery ka use karte hain. IN operator ka use karte hue hum ek column ke values ke saath compare karte hain, aur agar koi bhi value list mein ya subquery mein match ho jaati hai toh queri oska data return kar deti hai.

Syntax :
~~~
SELECT * FROM table_name WHERE column_name IN(column_value);
~~~

Example :
```sql
SELECT * FROM students WHERE studentId IN (1,2,3,4,5);
```

- #### LIKE operator

LIKE operator ka use text ki values mein specific pattern ya substring ke saath match karna ke liye hota hai. Is operator mein aap wildcard characters jaise ki % aur _ ka bhi upyog kar sakte hai.


> ##### LIKE with % searchValue.

% se pahal kuch bhi ho sakta hai lakin oske aage searchValue honi chahiye.

Syntax :
~~~
SELECT * FROM table_name WHERE column_name LIKE '% searchValue'
~~~

Example :
```sql
SELECT * FROM students WHERE studentName LIKE '%khan';
```

> ##### LIKE with % searchValue %;

% se pahal or % ke bade kuch bhi ho sakta hai. lakin bich me searchValue honi chahiye.

Syntax :
~~~
SELECT * FROM table_name WHERE column_name LIKE '% searchValue %'
~~~

Example :
```sql
SELECT * FROM students WHERE studentEmail LIKE '%khan12@gmail%';
```

> ##### LIKE with searchValue %

% ke bade kuch bhi ho sakta hai lakin pahal searchValue honi chahiye.

Syntax :
~~~
SELECT * FROM table_name WHERE column_name LIKE 'searchValue %'
~~~

Example :
```sql
SELECT * FROM students WHERE mobileNuber LIKE '1234%';
```

- #### BETWEEN operator

BETWEEN operator DBMS mein ek tarah ka comparison operator hai jisse hum values ki range ko specify kar sakte hain. Iska use hum tab karte hain jab hume kisi column ki values ko ek range mein filter karna hota hai.

Syntax :
~~~
SELECT * FROM table_name WHERE column_name BETWEEN value AND value;
~~~

Example :
```sql
SELECT * FROM students WHERE studentId BETWEEN 5 AND 8;
```

- #### EXISTS operator

DBMS mein EXISTS operator ka upyog database mein data ki maujoodgi ko check karne ke liye kiya jaata hai. Is operator ke saath hum ek subquery ka upyog karte hain jismein hum check karte  hain ki kya vah record table maujood hai ya nahin.Agar subquery se koi record return hota hai to EXISTS operator true return karta hai aur agar koi record nahi return hota hai to false return karta hai.Agar EXISTS operator true return karta hai to maine queri data return karti hai otherwis data return nhi hota hai.

Syntax :
~~~
SELECT * FROM table_name WHERE EXISTS (SELECT * FROM table_name WHERE condition);
~~~

Example :
```sql
SELECT * FROM students WHERE EXISTS(SELECT * FROM students WHERE studentName = "wecode");
```

- #### ALL operator

ALL operator ek database management system (DBMS) mein ek operator hai jo comparison operators ke saath use kiya jaata hai. Is operator ko comparison operator ke baad likha jaata hai aur yeh sabhi values ko return karta hai jo comparison operator se compare ki jaati hai.Agar condition true hoti hai to maine queri data return karti hai otherwis data return nhi karti hai.

Syntax :
~~~
SELECT * FROM table_name WHERE condition ALL (SELECT column_name FROM table_name WHERE condition)
~~~

Example :
```sql
SELECT * FROM students WHERE studentId >= ALL (SELECT studentId FROM students WHERE fatherName = 'wecode khan');
```

- #### ANY operator

ANY operator ka use table me particular value ke sath koi record fill hai ya nhi yhe dekhane ke liye kiya jaya hai. or record fill hota hai to sub queri jo data retrun karti hai. os maine queri se compare karte hai. comparision ke according main queri data return karti hai.

Syntax :
~~~
SELECT * FROM table_name WHERE condition ANY (SELECT column_name FROM table_name WHERE condition);
~~~

Example :
```sql
SELECT * FROM students WHERE studentId <= ANY (SELECT studentId FROM students WHERE studentId > 4);
```

## CONSTRAINT in DBMS

DBMS mein constraint ek rule hai jo database table ke data ko limit karta hai. Constraint ka upyog data consistency aur data accuracy ko maintain karne ke liye kiya jata hai. Constraints table level ya column level par apply kiye ja sakte hai.

Syntax :
~~~
CREATE TABLE Table_name (
Column1 DATATYPE CONTRAINT,
Column2 DATATYPE CONTRAINT,
...
);
~~~

Example :
```sql
CREATE TABLE fees(
feeId INTEGER UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT,
amount BIGINT NOT NULL CHECK (amount >= 3000),
month VARCHAR(155) NOT NULL,
feesCheck VARCHAR(155) DEFAULT 'Yes',
sId INTEGER FOREIGN KEY(sId) REFERENCES students(studentId)
);
```

- **UNSIGNED** ka matlab hai ki yhe column me negative number allow nhi laga. 
- **PRIMARY KEY** ka matlab hai ki record ko uniquely identify karega. 
- **FOREIGN KEY** ka use do table ke bich relation bana ke liye hota hai.
- **NOT NULL** ka matlab hai ki column ki value null nhi ho sakti.
- **AUTO_INCREMENT** ka matlab hai ki **PRIMARY KEY** automatic increment hoti rahagi. 
- **DEFAULT** ka matlab hai ki column me value insert nhi ki gai to ye default value insert ho jaygi.
- **CHECK** constraint ka matlab hai ki column me condition ke accroding value insert ho sakti hai.

## JOINs in DBMS

Joins ka use do ya do se jyada table ko combine kar ke data get karne ke liye hota hai.

- #### INNER JOIN

Inner join ka use do ya do se jyada table ki coman record ko get karane ke liye hota hai.INNER JOIN ka use karte hue, hum do alag tables mein se information extract karke unhein ek hi table mein display kar sakte hai. Is tarah hume ek naya table milta hai jo dono tables ke information ko combine karta hai.

Syntax :
~~~
SELECT * FROM table_name INNER JOIN table_name ON condition;
~~~

Example :
```sql
SELECT * FROM students INNER JOIN fees ON student.sId IN(fees.sId);
```

- #### LEFT JOIN

LEFT JOIN ek database query hai jiske dwara hum do alag-alag tables ke beech ka connection establish kar sakte hai. Ismein, hum left table se sabhi records ko select karte hai aur uske saath right table se matching records bhi select karte hai. Agar koi matching record nahi hota hai toh bhi left table ke saare records display hote hai, par right table ke records NULL (khali) hote hai.

for Example students or fees ke coman record or students ke sare record get honge.

Syntax :
~~~
SELECT * FROM table_name LEFT JOIN table_name ON condition;
~~~

Example :
```sql
SELECT * FROM students LEFT JOIN fees ON student.sId IN(fees.sId);
```

- #### RIGHT JOIN

RIGHT JOIN ek database query hai jiske dwara hum do alag-alag tables ke beech ka connection establish kar sakte hai. Ismein, hum right table se sabhi records ko select karte hai aur uske saath left table se matching records bhi select karte hai. Agar koi matching record nahi hota hai toh bhi right table ke saare records display hote hai, par left table ke records NULL (khali) hote ha

for Example students or fees ke coman record or fees ke sare record get honge.

Syntax :
~~~
SELECT * FROM table_name RIGHT JOIN table_name ON condition;
~~~

Example :
```SQL
SELECT * FROM students RIGHT JOIN fees ON student.sId IN(fees.sId);
```

## MULTIPLE JOINs

DBMS mein "multiple join" ka matlab hai ki aap ek se adhik tables ko join kar rahe hain. Jab aap do ya do se adhik tables ko join karte hain, toh aap in tables ke beech ki ek ya ek se adhik common columns ka istemal kar sakte hain.

- #### MULTIPLE INNER JOIN

Multiple Inner Join ek database management system (DBMS) ka query hai jisme multiple tables se data retrieve karne ke liye use hota hai. Ismein Inner Join ka use hota hai jiski madad se do ya do se zyada tables ke beech common data ko combine kiya jata hai.

for example students or fees or result table ke subi comman record combine honge.

Syntax :
~~~
SELECT * FROM table_name INNER JOIN table_name ON condition INNER JOIN table_name ON condition;
~~~

Example :
```sql
SELECT * FROM students INNER JOIN fees ON student.sId IN(fees.sId) JOIN result ON student.sId IN(result.sId);
```

- #### MULTIPLE LEFT JOIN

MULTIPLE LEFT JOIN ek database query hai jiske dwara hum do ya do se jyada tables ke beech ka connection establish kar sakte hai. Ismein, hum left table se sabhi records ko select karte hai aur uske saath right table se matching records bhi select karte hai. Agar koi matching record nahi hota hai toh bhi left table ke saare records display hote hai, par right table ke records NULL (khali) hote hai.

for example students or fees or result table ke subi comman record and fees or result ke subi data combine honge.

Syntax :
~~~
SELECT * FROM table_name LEFT JOIN table_name ON condition LEFT JOIN table_name ON condition;
~~~

Example :
```SQL
SELECT * FROM students LEFT JOIN fees ON student.sId IN(fees.sId) LEFT JOIN result ON student.sId IN(result.sId);
```

- #### MULTIPLE RIGHT JOIN.

MULTIPLE RIGHT JOIN ek database query hai jiske dwara hum do ya do se jyada tables ke beech ka connection establish kar sakte hai. Ismein, hum right table se sabhi records ko select karte hai aur uske saath left table se matching records bhi select karte hai. Agar koi matching record nahi hota hai toh bhi right table ke saare records display hote hai, par left table ke records NULL (khali) hote hai.

for example students or fees or result table ke subi comman record and students or fees ke subi data combine honge.

Syntax :
~~~
SELECT * FROM table_name RIGHT JOIN table_name ON condition RIGHT JOIN table_name ON condition;
~~~

Example :
```SQL
SELECT * FROM students RIGHT JOIN fees ON student.sId IN(fees.sId) RIGHT JOIN result ON student.sId IN(result.sId);
```

## VEIW IN DBMS

DBMS mein, ek view ek virtual table hai jo ek ya ek se adhik pahle se maujood table se derive kiya gaya hota hai. Iske alawa, view mein khude ka koi data nahi hota hai. Balki, ye ek SQL query dwara define kiya jata hai jo underlying tables se data select aur organize karta hai.Views ka upyog complex queries ko simplify karne, alag-alag users ya applications ke liye data ka ek simplified ya restricted view provide karne ke liye, ya sensitive data ko protect karne ke liye kiya jata hai. Ye multiple tables se data ko aggregate karne ya different sources se data ko combine karne ke liye bhi upyogi hai.

- #### Create view with single table

Syntax :
~~~
CREATE VIEW view_name AS 
SELECT column_name1, column_name2, column_name3, ...
FROM table_name 
~~~

Example :
```sql
CREATE VIEW studentsRecord AS 
SELECT studentName, fatherName, mobileNumber 
FROM students;
```

- #### Create view with single table and condition

Syntax :
~~~
CREATE VIEW view_name AS 
SELECT column_name1, column_name2, column_name3, ...
FROM table_name WHERE condition;
~~~

Example :
```sql
CREATE VIEW studentsRecord AS 
SELECT studentName, fatherName, mobileNumber 
FROM students WHERE studentId = 3;
```

- #### Create view with multiple table and using joins

Syntax :
~~~
CREATE VIEW view_name AS 
SELECT column_name1, column_name2, column_name3, ...
FROM students JOIN fees ON studentId = feesId
~~~

Example :
```sql
CREATE VIEW studentsRecord AS 
SELECT studentName, fatherName, mobileNumber, feeId, feeAmount, feeMonth
FROM students JOIN fees ON studentId = feeId;
```

- #### Get data in view

Select command ka use karke view se record get kiya ja sakta hai.

Syntax :
~~~
SELECT * FROM view_name;
~~~

Example :
```sql
SELECT * FROM studentsRecord;
```

- #### Update view

Alter command ka use karke view ko update karne ke liye bhi kiya ja sakta hai.

Syntax :
~~~
ALTER VIEW view_name AS 
SELECT update_column1, update_column2, update_column3,
FROM table_name JOIN table_name ON condition;
~~~ 

Example :
```sql
ALTER VIEW studentsRecord AS
SELECT studentName, subject, mobileNumber, feeId, feeAmount, feeMonth
FROM students JOIN fees ON studentId = feeId;
```

## UNION IN DBMS

Union ek database management system (DBMS) mein ek SQL operator hai, jo do ys do se adhik SELECT statements ko combine karke ek hi result set (output) deta hai. Union ka upyog do ya do se adhik tables se data ko combine karne ke liye kiya jata hai.Union ke dwara, do ya do se adhik tables mein se distinct rows ko combine kiya jata hai. Iske liye, Union operator ka upyog karte hue, dono queries mein ek hi number ke columns hone chahiye, aur ye columns ek dusre se compatible hone chahiye, matlab same data type ka hona chahiye. Union operator ke baad jo result set generate hota hai, wo distinct rows ko hi include karta hai, duplicate rows ko nahi karta.

Syntax :
~~~
SELECT column_name1, column_name2, column_name3 FROM table_name WHERE condition
UNION 
SELECT column_name1, column_name2, column_name3 FROM table_name WHERE condition
~~~

Example :
```sql
SELECT studentId, fatherName, mobileNumber FROM students WHERE studentId = 3
UNION
SELECT feeId, feeMonth, feeAmount FROM fees WHERE studentId = 3;
```

## CREATE INDEX IN DBMS

Create Index DBMS mein ek command hai, jo ek table ke ek ya adhik column ko index karta hai, jisse table ke data ko faster access karne mein madad milti hai. Index ek data structure hai, jo table ke columns ke values ko organize karta hai, taki queries ko execute karte waqt data ko jaldi se retrieve kiya ja sake.Index ka upyog large tables mein data ko search karte samay performance ko optimize karne ke liye kiya jata hai. Jab koi query table ke column ke values ke basis par search karta hai, to index query execution time ko reduce kar deta hai, kyunki index mein data organized hota hai, jisse specific rows ko retrieve karna aasan ho jata hai.

Syntax :
~~~
CREATE INDEX index_name ON table_name(column1,column2, ...); 
~~~

Example :
```sql
CREATE INDEX studName_index ON students(studentName,fatherName);
```

- #### Create index with unique

Create index with unique ek database management system (DBMS) mein ek command hai, jiski madad se hum ek table mein unique index create kar sakte hai. Index ka upyog table ke rows ko fast access karne ke liye kiya jata hai. Jab hum table mein kisi column par unique index create karte hai, to us column mein duplicate values nahi ho sakte hai.

Syntax :
~~~
CREATE UNIQUE INDEX index_name ON table_name(column1,column2, ...); 
~~~

Example :
```sql
CREATE UNIQUE INDEX studName_index ON students(studentName,fatherName);
```

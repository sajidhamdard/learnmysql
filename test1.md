### How to create the student table in MySQL?

CREATE TABLE `student` ( 
 `studentid` int(10) UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `name` varchar(255) , 
 `email_address` varchar(255), 
 `city` varchar(255) , 
 `fathername` varchar(255),
 `mobile` int(15)
);

### How to create the fees table in MySQL?

CREATE TABLE `fees` ( 
 `feeid` integer UNSIGNED PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `amount` bigint,
 `month` varchar(255),
 `studentid` int unsigned,
 CONSTRAINT FK_StudentId FOREIGN KEY (studentid)
	REFERENCES Student(studentid)
);

### How to insert a new fee record into the fees table for a particular student?

INSERT INTO fee (amount, month, studentid) VALUES (5000 ,'Jan', 1);

### How to update a student record in the student table?

update student set fieldname = value, field2=value where condition;

### How to update a fee record in the fees table?

update fee set fieldname = value, field2=value where condition;

### How to select all the records from the fees table?

select * from fee;

### How to select a particular student record from the student table?

select * from student where condition;

### How to select all the fee records for a particular student from the fees table?

select * from fee where studentid  = ?;

### How to get the total number of students in the student table?

select count(*) from student;

### How to get the sum of all the fees paid by a particular student?

select sum(amount) from fee where studentid = ?;

### How to get the average fee paid by all the students?

select avg(amount) from fee;

### How to get the student record with the highest mobile number in the student table?

select max(mobile) from student;

### How to get the fee record with the highest fee amount in the fees table?

select max(amount) from fee;

### How to get the list of all students who live in a city?

select * from student where city = ?;

### How to get the list of all cities along with the count of students living in each city?

select city,count(studentid) from student group by city;

### How to get the list of all cities along with the count of students living in each city, where the count is greater than 1?

select city,count(studentid) as total from student group by city having total > 1;

### How to get the list of all students sorted by their names in ascending order?

select * from student order by name asc;

### How to get the list of all students sorted by their mobile numbers in descending order? 

select * from student order by mobile desc;

### How to get the list of all fees records sorted by the fee amount in descending order?

select * from fee order by amount desc;

### How to get the list of all fees records sorted by the fee amount in descending order, for a particular student?

select * from fee where studentid = ? order by amount desc;

create database college_2;
use college_2;
create table Department
( department_id int primary key,
department_name varchar (50) unique not null );
create table student_1
( roll_no int primary key,
name varchar (50) not null,
email_id varchar (50) unique,
aadhar_no varchar (12) unique,
department_id int,
foreign key (department_id) references
department (department_id));
create table Course_1
(course_1_name varchar (50) not null,
course_1_id int primary key,
department_id int,
foreign key (department_id) references
Department(Department_id));
Create Table Enrollment_1
(roll_no int, course_1_id int, sem int
check (sem between 1 and 8),
grade char(2),
primary key (roll_no, course_1_id, sem),
foreign key (roll_no) references student_1
(roll_no),
foreign key (course_1_id) references Course_1
(course_1_id));
insert into Department (Department_id, Department_name)
values(1,'ECE'), (2,'ECS');
select*from Department;
insert into student_1(roll_no, name, email_id, aadhar_no, department_id)
values ('101', 'Savi', 'savi@gmail.com', '326729751921', 1),
('102', 'Mason', 'mason@gmail.com', '286378420156', 2);
select*from student_1;
insert into Course_1
(course_1_id, course_1_name, department_id)
values(1, 'DAA', 1), (2, 'DBMS', 2);
select*from Course_1;
insert into Enrollment_1 (roll_no, course_1_id, sem, grade)
values (101,1,1,'B'), (102,2,2,'A');
select*from Enrollment_1;

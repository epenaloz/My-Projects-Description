# Descriptions of assignments done in Foundations of Data Management

NOTE: SQL and other was used using Amazon Web EC2 Instances.

## Homework 1: Firebase
I was tasked to connect to a database in Firebase and generate 7 Python files to add and find data within the database. The 7 files consisted of: add_course, add_instructor, add_student, find_instructor_courses, find_student_courses, take_course, and teach_course. Each Python file takes in 3 inputs in the command line; the code will check or raise expectations when needed and update the database.
Libraries used: JSON, Sys, Requests

## Homework 2: XML Database
Similar to HW1, instead of using Firebase, we used an XML document as our database. Based on inputs, the code will update, check, or raise exceptions if needed.
Libraries used: lxml import etree, sys

## Homework 3: SQL Database
The following schema is regarding a Course Management DB

Course(number, title, semester)

Student(id, name, program)

Instructor(id, name, department)

Take(sid, cno, semester)

Teach(rid, cno, semester)

TA(sid, hours)

Assist(sid, cno, semester)

I was tasked to generate a sample SQL database of the above schema, add data, and query the data.

Some queries answered were the following: Finding out which courses are offered in Spring 2023 but not Fall 2023, Finding out for each instructor the average number of students are in their Fall 2023 courses, Finding out which courses offered in Fall 2023 only have one TA, Finding out which instructors teach the largest number of courses in Fall 2023, Finding out which students did not take any courses in Fall 2023, Finding students who have taken two distinct classes, and Finding out which courses contain "data" in their title. 

After adding data and querying it, I was tasked with generating a Python file to find courses, taking in the student ID as input and outputting the student's name, program, and titles and semesters of all courses taken by that student. 

Files: db.sql, find_course.py
Libraries used: sqlalchemy, pymysql, pandas, sys

## Homework 4: CSV Database
I was tasked with storing a table with the following schema: person(id int primary key, name varchar(20), gender char(1)), in a CSV file where each line represents a person record.
I was tasked to write two Python files.

insert.py => that inserts a new person into the table, not allowing the insertion to proceed if it violates the primary key or other constraints.

search.py => returns the records of students witha  given name 



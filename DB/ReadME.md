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

insert.py => inserts a new person into the table, not allowing the insertion to proceed if it violates the primary key or other constraints.

search.py => returns the records of students with a given name 

I was also tasked to manually calculate/explain the steps for joining algorithms such as sorting, partition hashed join, sort-merge join, block-based, and nested loops, indicating the sizes of output for each step, the total number of I/Os needed for each algorithm, and showing which algorithm was most efficient in terms of I/Os.


## Homework 5: Hadoop and Spark, Map Reduce
### Task 1: Map Reduce
I was tasked to edit a Map Reduce Program to answer an SQL query based on sales.csv data that contained 3,861 rows. Each row has the following values: store, product, unit, holiday, price, and base.

The SQL query that needed to be answered was the following: 
SELECT store, product, max(weekly_unit_sold) FROM sales WHERE is_holiday = 'FALSE' and base_price > price GROUP BY store, product HAVING count(*) >=21;

This was run in hadoop EC2 instance, I modified the java file of the map reduce code to output necessary data for the query.

Since our data was in the form of columns in a CSV file, the map portion of my code will split the CSV rows into tokens. Then a conditional statement will check if the holiday token is false and base price is greater than the price, if the conditional statement is true the map will output ("store + product", unit).

The reduce portion of my code will focus on returning the max of the weekly units sold. Using IntWritable, we will get the value of the unit and increase the count by 1. We initialize count to be 0 and max to be 0. If the unit value exceeds the max, we update max to that value. 
Finally, if the count exceeds 21, we set our result to the current max and output (key, max).


### Task 2: Spark and Spark RDD 
The next task used data from the following JSON files: country.json, city.json, and countrylaunguage.json. 

I was tasked to write a Spark Datarame script for certain queries. Then, do the same queries but in Spark RDD. The following queries I answered are below:

1. Finding top-10 most populated cities, and return the cities and populations in descending order
2. Finding out the top 3 most popular official languages based on the number of countries that speak the language
3. Finding out the names of countries in North America that have at least two official languages
4. Finding out the names of countries in Europe which have English as their official language
5. Finding out the names of countries where English is an official language and French is an unofficial language.

## Lab 3: Mongo DB
Similar to the Course Database Management assignments as before, I was tasked to create my own sample database of the following collections:

Course(number, title, semester)

Student(id, name, program)

Instructor(id, name, department)

Take(sid, cno, semester)

Teach(rid, cno, semester)

### Task 1: Mongo DB Functions to query the data
I was tasked to answer the following queries in Mongo DB

1. Find the name and program of students who are between 25 and 30 years old (inclusive).
2. Find out which courses are offered in Fall 2023. Report course number and title.
3. Find out titles of courses in Fall 2023 that contain “data”.
4. Find out which students have taken DSCI 551 in Fall 2023. Report both student ids and names.
5. Find out which students did not take any courses in Fall 2023. Report only the student ids.
6. Find out for each instructor the number of courses (i.e., how many courses) he/she teaches in Fall 2023.


### Task 2: PyMongo Python Scripts
I was tasked to write 3 Python scripts using Pymongo to get data from my Mongo DB. The following queries I had to answer are below.

1. Find out which courses are offered in Fall 2023. Reporting Course number and titles.
2. Finding out which students have taken two distinct classes, reporting student IDs
3. Finding out which students have taken a distinct  course but not another, reporting student IDs
4. Finding out which instructors teach the largest number of courses in the Fall 2023 reporting instructor IDs.


## Lab 4: DynamoDB
I was tasked to create a table in DynamoDB containing data of two people with multiple attributes randing from strings, maps, numbers, booleans, lists etc.


## Final Project: Implement a sample database system
I was tasked to implement a sample database system that can support a data model such as a relational one. The system should have its own query language that differs from what is out there and can do projection, filtering, selection, joining, grouping, aggregating, and ordering. The system should be able to insert, delete, or update the data.

My databse system will start off by asking the user what dataset they would like to choose from based on the file system. Once a file is chosen, it will call a method that will do chunking, which will chunk the data by 1000 and then return a data frame. If my database uses methods like filtering or getting a subset of rows in the data, it will still do chunking.
Since the use of pandas was limited, we had to code the joining, aggregation, and grouping using methods other than pandas - like numpy for getting min max, etc.

For my project, I did a relational model using CSV to store the data. My databse system has an interactive command line as shown below.
![Screenshot 2024-08-28 at 5 54 31 PM](https://github.com/user-attachments/assets/e086aea1-1ded-4152-ae2e-79617e5d25d8)

Joining methods would generate a new CSV file and use a CSV reader that opens the dataset, reads the rows, and returns the data based on the left, right, outer, or inner joins of the two datasets on given criteria. 


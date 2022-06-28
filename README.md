# SQL Queries

In this challenge you'll be be writing a number of different SQL queries against our school database. Once you have a working query, check your work against the database.

For submission of this challenge, touch a new file with the SQL statements you've written to get the desired result.


### Select all rows from the `classes` table.
 select * from classes;

### Select the `name` and `credits` from the `classes` table where the number of credits is greater than 3.
<!-- select name_class, credits from classes where credits > 3; -->

### All rows from the `classes` table where credits is an even number.
<!-- select * from classes where credits % 2 = 0; -->

### All of Tianna's enrollments that she hasn't yet received a grade for.
<!-- select * from enrollments where enrollments.student_id = 1 and enrollments.grade is null; -->

### All of Tianna's enrollments that she hasn't yet received a grade for, selected by her first name, not her `student.id`
<!-- select classes.name_class from students join enrollments on students.id = enrollments.student_id join classes on classes.id = enrollments.class_id where enrollments.grade is null and students.first_name = 'Tianna'; -->

### All of Tianna's enrollments that she hasn't yet received a grade for, selected by her first name, not her `student.id`, with the class name included in the result set.
<!-- select students.first_name, classes.name_class from students join enrollments on students.id = enrollments.student_id join classes on classes.id = enrollments.class_id where enrollments.grade is null and students.first_name = 'Tianna'; -->

### All students born before 1986 who have a 't' in their first or last name.
<!-- select first_name from students where birthdate < '1986-01-01' and lower(last_name) like '%t%' or lower(first_name) like '%t%'; -->

### The average age of all the students.
<!-- select avg(age(current_date, birthdate)) from students; -->

### Addresses that have a space in their city name.
<!-- select * from addresses where city like '% %'; -->

### Students & their addresses that live in a city with more than one word in the city name.
<!-- select students.first_name, addresses.line_1 from students join addresses on students.address_id = addresses.id where addresses.city like '% %' -->

### The average number of credits for classes offered at the school.
<!-- select avg(credits) from classes; -->

### The first and last name of all students who have received an 'A'.
<!-- select students.first_name, classes.name_class from students join enrollments on students.id = enrollments.student_id join classes on classes.id = enrollments.class_id where enrollments.grade = 'A'; -->

### Each student's first name and the total credits they've enrolled in
<!-- select students.first_name, sum(classes.credits) from students join enrollments on students.id = enrollments.student_id join classes on classes.id = enrollments.class_id group by students.first_name -->

### The total number of credits each student has received a grade for.
<!-- select students.first_name, sum(classes.credits) from students join enrollments on students.id = enrollments.student_id join classes on classes.id = enrollments.class_id where enrollments.grade is not null group by students.first_name; -->

### All enrollments, including the class name.
<!-- select distinct students.first_name, classes.name_class from students join enrollments on students.id = enrollments.student_id join classes on classes.id = enrollments.class_id order by students.first_name; -->

### Students born between 1982-1985 (inclusive).
<!-- select first_name, last_name from students where students.birthdate between '1982-01-01' and '1985-12-31'; -->

### Insert a new enrollment recording that Andre Rohan took PHYS 218 and got an A.

<!-- insert into enrollments(student_id, class_id, grade) values (5, 4, 'A'); -->
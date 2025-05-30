![image](https://github.com/user-attachments/assets/1558f3eb-312b-4929-9b22-66512a046b53)# postgresql


![image](https://github.com/user-attachments/assets/85691498-a855-4a33-8480-0ac1831afb21)

![image](https://github.com/user-attachments/assets/e925969e-e370-4a3d-81f4-7780a4acb618)

![image](https://github.com/user-attachments/assets/5c0f292c-10d2-452a-b9e0-008b65f3c705)

![image](https://github.com/user-attachments/assets/deeafc4f-a59f-4f74-b0d4-44a5b20f67ca)

![image](https://github.com/user-attachments/assets/d93ead44-7518-443f-923e-dc33ac6ca24c)

Inserting values into the students table:
![image](https://github.com/user-attachments/assets/b4935355-6011-4e35-80fa-7ed6bbbbb85e)

![image](https://github.com/user-attachments/assets/0a49897e-2258-41c6-bcb7-44111f54ad79)


Selecting columns in the table:

![image](https://github.com/user-attachments/assets/c90e21ea-ea90-48db-90f6-86715bdff91d)

Where clause:

![image](https://github.com/user-attachments/assets/455c1110-2b02-41c2-a33e-525db164f66a)

![image](https://github.com/user-attachments/assets/8a89e8f9-7748-4540-bccb-f91fa66da095)

Between:

![image](https://github.com/user-attachments/assets/f1741cca-bfb5-4dec-b83a-d3c142374bfb)

LIKE:

![image](https://github.com/user-attachments/assets/eeba34ea-1249-4eba-937c-8d96adf8c4c6)

![image](https://github.com/user-attachments/assets/9a74a082-3625-4e0f-ba99-e1f4a019c190)

![image](https://github.com/user-attachments/assets/24b0a84a-e05c-432f-b947-d87c4dd8b402)

![image](https://github.com/user-attachments/assets/0036815b-882a-4cef-8dd5-5e8064c63e66)

IN:

![image](https://github.com/user-attachments/assets/4e616440-8f91-4cd1-b865-7214aee7857e)

![image](https://github.com/user-attachments/assets/6e1d7eb8-84dd-4ffc-8436-7eccb259a891)

IS NULL and IS NOT NULL

![image](https://github.com/user-attachments/assets/5b615638-cb79-4612-bcb5-f59b1792848b)


- **Activity:**  practice various `SELECT` queries with `WHERE` clauses:
    - Find the student with `student_id` 2.33

![image](https://github.com/user-attachments/assets/df6061b4-e8d6-4b99-8566-dfe814b388ae)


    - Find all students born before January 1st, 2003.
 
![image](https://github.com/user-attachments/assets/9c06f501-5209-4bff-a5ed-a04590aa35e1)


    - Find students whose first name starts with 'B' or 'C'.

![image](https://github.com/user-attachments/assets/7966863e-32fe-4bf4-944b-60f2bdd9a44e)


    - Find students whose email address is from `example.com`.

![image](https://github.com/user-attachments/assets/01a25cbb-c314-4b12-8cdf-e8296969dd60)


    - Find students who do *not* have an email address listed.

![image](https://github.com/user-attachments/assets/d28760ba-058a-4f17-91a7-4190e57af17f)




UPDATE

![image](https://github.com/user-attachments/assets/e0f778fa-8d94-4e48-b639-38cc2e025b4e)


ACTIVITY:

![image](https://github.com/user-attachments/assets/7e0f340b-3149-4be8-8d45-946820f427d4)






DELETE:

![image](https://github.com/user-attachments/assets/f555fb08-740d-4fc9-ae4a-c7bc9f658cd8)


ORDER BY:


![image](https://github.com/user-attachments/assets/a1fd1299-d430-4420-ba43-b2e79d85c97e)

![image](https://github.com/user-attachments/assets/8cd16ca4-5a93-45ce-816d-4af6113863d3)

![image](https://github.com/user-attachments/assets/422f8f4d-dc02-441b-b50a-6d4a52c749cc)


ACTIVITY:

- List all students ordered by their date of birth, oldest first.

![image](https://github.com/user-attachments/assets/6630c653-e841-446f-9859-518c99758b2f)

- List all students ordered by last name descending, then by first name ascending.

![image](https://github.com/user-attachments/assets/a947a32c-2bd6-4954-8050-eea4d16c95a1)


LIMIT and OFFSET:

![image](https://github.com/user-attachments/assets/e5b85952-7407-42b1-b0a7-17177258a6a6)

![image](https://github.com/user-attachments/assets/d40dd649-b3b2-4bed-8c4e-253c71f230d8)


ACTIVITY:


- Find the two students who were born earliest (oldest two).

![image](https://github.com/user-attachments/assets/02240abf-9531-4b08-823e-5d680c919e3c)


- List students, skipping the first one and showing the next two, ordered by `student_id`.

![image](https://github.com/user-attachments/assets/aa34c6d8-6452-41dd-be5b-3b4f56f56643)



Removing Duplicates: DISTINCT

university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (5, 'Eve', 'Smith', 'eve.smith@example.com', '2004-07-01');
INSERT 0 1
university_db=> SELECT last_name FROM students;
 last_name
-----------
 Johnson
 Bhima

 Smith
 Kelam
 Brown
 Prince
 Smith
(8 rows)


![image](https://github.com/user-attachments/assets/bb06e4ed-34ce-478b-8581-2939b2579c96)


university_db=> SELECT DISTINCT last_name FROM students ORDER BY last_name;
 last_name
-----------
 Bhima
 Brown
 Johnson
 Kelam
 Prince
 Smith

(7 rows)


university_db=> SELECT DISTINCT last_name, first_name FROM students;
 last_name | first_name
-----------+-------------
           | anil
 Prince    | Diana
 Kelam     | Keerthi
 Bhima     | Meghana sai
 Smith     | Eve
 Smith     | Alice
 Brown     | Charlie
 Johnson   | Bob
(8 rows)


![image](https://github.com/user-attachments/assets/7f87522e-23be-4e6b-9803-c8e77d0a532d)


ACTIVITY:

Get a list of unique birth years from the students table.


university_db=> SELECT DISTINCT dob FROM students ORDER BY dob;
    dob
------------
 2001-11-01
 2002-05-15
 2002-08-22
 2003-02-15
 2003-12-22
 2004-06-28
 2004-07-01

(8 rows)



university_db=> SELECT DISTINCT EXTRACT(YEAR FROM dob) AS birth_years FROM students ORDER BY birth_years;
 birth_years
-------------
        2001
        2002
        2003
        2004

(5 rows)





![image](https://github.com/user-attachments/assets/45f34643-5334-4001-b671-79f33fdc7261)

![image](https://github.com/user-attachments/assets/4e648f8b-6b40-40fb-a1b9-8dd4aa609708)



Aggregate Functions:

university_db=> SELECT COUNT(*) AS total_students FROM students;
 total_students
----------------
              8
(1 row)


university_db=> SELECT COUNT(email) AS students_with_email FROM students;
 students_with_email
---------------------
                   7
(1 row)


university_db=> SELECT COUNT(DISTINCT last_name) AS unique_last_names FROM students;
 unique_last_names
-------------------
                 6
(1 row)


university_db=> SELECT MIN(dob) AS oldest_student_dob FROM students;
 oldest_student_dob
--------------------
 2001-11-01
(1 row)


university_db=> SELECT MAX(dob) AS youngest_student_dob FROM students;
 youngest_student_dob
----------------------
 2004-07-01
(1 row)


![image](https://github.com/user-attachments/assets/da4e8b9b-ffc8-458f-b0c9-519e233eebd2)


![image](https://github.com/user-attachments/assets/55a8345c-8441-4a08-856d-61bf4f6fecbf)


ACTIVITY:

- Count how many students are in the `students` table.

university_db=> SELECT COUNT(*) AS total_students FROM students;
 total_students
----------------
              8
(1 row)

![image](https://github.com/user-attachments/assets/b2472d08-770b-4aa3-9944-0f6054a463c0)


- Find the earliest (minimum) date of birth.

university_db=> SELECT MIN(dob) AS oldest_student_dob FROM students;
 oldest_student_dob
--------------------
 2001-11-01
(1 row)

![image](https://github.com/user-attachments/assets/7767afbc-d902-481c-8dba-6d322d41b390)

  
- Count how many distinct last names there are.

university_db=> SELECT COUNT(DISTINCT last_name) AS unique_last_names FROM students;
 unique_last_names
-------------------
                 6
(1 row)

![image](https://github.com/user-attachments/assets/728e43be-aa46-405b-bcd0-e181c6142b5c)




university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          5 | Eve         | Smith     | eve.smith@example.com     | 2004-07-01
(8 rows)



![image](https://github.com/user-attachments/assets/5ff1aa05-dac0-49bf-8884-16e7422aab46)



GROUP BY:

-- Count students for each last name

university_db=> SELECT last_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY last_name
university_db-> ORDER BY number_of_students DESC;
 last_name | number_of_students
-----------+--------------------
 Smith     |                  2
 Johnson   |                  1
           |                  1
 Bhima     |                  1
 Prince    |                  1
 Brown     |                  1
 Kelam     |                  1
(7 rows)


![image](https://github.com/user-attachments/assets/bb5ddf67-2f70-4dba-ac37-2a5d3875cccc)


-- Count students for each last name, only for last names with more than one student

university_db=> SELECT last_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY last_name
university_db-> HAVING COUNT(*) > 1
university_db-> ORDER BY number_of_students DESC;
 last_name | number_of_students
-----------+--------------------
 Smith     |                  2
(1 row)


![image](https://github.com/user-attachments/assets/22decd18-924a-4ed1-8d12-55b81c7f8d76)


-- PostgreSQL specific way to get year from date: EXTRACT(YEAR FROM date_column)

SELECT EXTRACT(YEAR FROM dob) AS birth_year, COUNT(*) AS students_in_year
FROM students
WHERE dob IS NOT NULL
GROUP BY birth_year
ORDER BY birth_year;


![image](https://github.com/user-attachments/assets/5440d8fa-ea11-4da1-82e3-bb349592edc2)


- **Activity:**
    - Count the number of students for each distinct first`_name`.

 university_db=> SELECT first_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY first_name
university_db-> ORDER BY number_of_students DESC;
 first_name  | number_of_students
-------------+--------------------
 anil        |                  1
 Keerthi     |                  1
 Eve         |                  1
 Meghana sai |                  1
 Alice       |                  1
 Bob         |                  1
 Charlie     |                  1
 Diana       |                  1
(8 rows)


![image](https://github.com/user-attachments/assets/0aa0b4c3-5b26-4c53-aaab-46c50e99f753)


    - Find the number of students born in each year.


university_db=> SELECT EXTRACT(YEAR FROM dob) AS birth_years, COUNT(*) AS count
university_db-> FROM students
university_db-> GROUP BY birth_years;
 birth_years | count
-------------+-------
             |     1
        2003 |     2
        2002 |     2
        2001 |     1
        2004 |     2
(5 rows)

![image](https://github.com/user-attachments/assets/cb42de34-474b-4c2a-b055-91567d1886f2)


Activity:


DROPPING THE TABLE AND CREATING IT AGAIN WITH CONSTRAINTS:

university_db=> DROP TABLE IF EXISTS students;
DROP TABLE
university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50) NOT NULL,
university_db(>     last_name VARCHAR(50) NOT NULL,
university_db(>     email VARCHAR(100) UNIQUE,
university_db(>     dob DATE,
university_db(>     enrollment_status VARCHAR(10) CHECK (enrollment_status IN ('enrolled', 'graduated', 'dropped'))
university_db(> );
CREATE TABLE


![image](https://github.com/user-attachments/assets/80375946-fe18-44df-89e4-537baf782465)




**-- Try inserting data that violates these:**

university_db=> INSERT INTO students (student_id, last_name, email, dob) VALUES (1, 'Test', 'test@test.com', '2000-01-01');
ERROR:  null value in column "first_name" of relation "students" violates not-null constraint
DETAIL:  Failing row contains (1, null, Test, test@test.com, 2000-01-01, null).


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob) VALUES (1, 'Test', 'User', 'test@test.com', '2000-01-01');
INSERT 0 1


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob) VALUES (2, 'Another', 'User', 'test@test.com', '2001-01-01');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(test@test.com) already exists.

university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob, enrollment_status) VALUES (2, 'Another', 'User', 'another@test.com', '2001-01-01', 'pending');
ERROR:  new row for relation "students" violates check constraint "students_enrollment_status_check"
DETAIL:  Failing row contains (2, Another, User, another@test.com, 2001-01-01, pending).


![image](https://github.com/user-attachments/assets/30b077ef-0dfc-410c-b51f-9efe9b9d4ba8)



KEYS:
Activity: 


university_db=> DROP TABLE IF EXISTS students;
DROP TABLE
university_db=> CREATE TABLE students (
university_db(>     student_id SERIAL PRIMARY KEY,
university_db(>     first_name VARCHAR(50) NOT NULL,
university_db(>     last_name VARCHAR(50) NOT NULL,
university_db(>     email VARCHAR(100) UNIQUE,
university_db(>     dob DATE,
university_db(>     enrollment_status VARCHAR(20) CHECK (enrollment_status IN ('enrolled', 'graduated', 'dropped', 'pending'))
university_db(> );
CREATE TABLE


![image](https://github.com/user-attachments/assets/ce3bbaab-546c-4201-9264-1a52c152fa5e)


university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Alice', 'Smith', 'alice.smith@example.com', '2003-05-15', 'enrolled');
INSERT 0 1
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Robert', 'Johnson', 'robert.j@example.com', '2002-08-22', 'enrolled');
INSERT 0 1
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10', 'pending');
INSERT 0 1
university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email           |    dob     | enrollment_status
------------+------------+-----------+---------------------------+------------+-------------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15 | enrolled
          2 | Robert     | Johnson   | robert.j@example.com      | 2002-08-22 | enrolled
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10 | pending
(3 rows)


![image](https://github.com/user-attachments/assets/e1cbbb8c-1f9a-4b32-a68d-7c7ba511f9db)



- Try inserting a student without an email. (Should work if `UNIQUE` constraint on email allows NULLs, which it does by default).

university_db=> INSERT INTO students (first_name, last_name, dob, enrollment_status)
university_db-> VALUES ('Sai', 'Brown', '2003-01-10', 'pending');
INSERT 0 1

university_db=> SELECT * FROM students;
 student_id | first_name | last_name |           email           |    dob     | enrollment_status
------------+------------+-----------+---------------------------+------------+-------------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15 | enrolled
          2 | Robert     | Johnson   | robert.j@example.com      | 2002-08-22 | enrolled
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10 | pending
          4 | Sai        | Brown     |                           | 2003-01-10 | pending
(4 rows)

![image](https://github.com/user-attachments/assets/4d1759ad-937e-4734-90c0-346e81f933e8)


- Try inserting a student with a duplicate email to one already existing. (Should fail due to `UNIQUE` constraint).

university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charliechar', 'BrownBear', 'charlie.brown@example.com', '2003-01-10', 'pending');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(charlie.brown@example.com) already exists.

![image](https://github.com/user-attachments/assets/bfc601c1-a16d-4161-911d-a690065e0497)

  
- Try inserting a student with a `NULL` first name. (Should fail due to `NOT NULL` constraint).

university_db=> INSERT INTO students (last_name, email, dob, enrollment_status)
university_db-> VALUES ('BrownBear', 'charlie.brown@example.com', '2003-01-10', 'pending');
ERROR:  null value in column "first_name" of relation "students" violates not-null constraint
DETAIL:  Failing row contains (6, null, BrownBear, charlie.brown@example.com, 2003-01-10, pending).

![image](https://github.com/user-attachments/assets/8621100a-dcfd-4099-aea2-6403927a0160)


- **Creating Tables for a Many-to-Many Relationship (Students and Courses):**

- Activity:

  
    1. **`courses` Table:**


university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMARY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10)
university_db(> );
CREATE TABLE
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Introduction to SQL', 3);
INSERT 0 1
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Database Design', 4);
INSERT 0 1
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Web Development', 3);
INSERT 0 1
university_db=> INSERT INTO courses (course_name, credits) VALUES ('Data Structures', 4);
INSERT 0 1

![image](https://github.com/user-attachments/assets/35a33e3d-3bc7-459f-8ead-bf308bee9db7)



2. **enrollments Table (Junction Table for Students and Courses):**

university_db=> CREATE TABLE enrollments (
university_db(>     enrollment_id SERIAL PRIMARY KEY,
university_db(>     student_id INTEGER NOT NULL,
university_db(>     course_id INTEGER NOT NULL,
university_db(>     enrollment_date DATE DEFAULT CURRENT_DATE,
university_db(>     grade CHAR(1) CHECK (grade IN ('A', 'B', 'C', 'D', 'F', 'W', NULL)),
university_db(>
university_db(>     CONSTRAINT fk_student
university_db(>         FOREIGN KEY (student_id)
university_db(>         REFERENCES students(student_id)
university_db(>         ON DELETE CASCADE,
university_db(>     CONSTRAINT fk_course
university_db(>         FOREIGN KEY (course_id)
university_db(>         REFERENCES courses(course_id)
university_db(>         ON DELETE RESTRICT,
university_db(>
university_db(>     UNIQUE (student_id, course_id)
university_db(> );
CREATE TABLE
university_db=>
university_db=>
university_db=> SELECT * FROM enrollments;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
(0 rows)


![image](https://github.com/user-attachments/assets/3a1fee1d-67be-4f46-b7a3-b1ed3a358e4b)


-- Try to insert an enrollment for a student_id that doesn't exist in students (e.g., student_id 999). It should fail due to FK constraint.

university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (999, 1, 'A');
ERROR:  insert or update on table "enrollments" violates foreign key constraint "fk_student"
DETAIL:  Key (student_id)=(999) is not present in table "students".

![image](https://github.com/user-attachments/assets/1a8bf685-50a4-42ff-b97e-8b0544d1c8bb)

-- Try to insert an enrollment for a course_id that doesn't exist in courses. It should fail.

university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 90, 'A');
ERROR:  insert or update on table "enrollments" violates foreign key constraint "fk_course"
DETAIL:  Key (course_id)=(90) is not present in table "courses".

![image](https://github.com/user-attachments/assets/6fbadcaa-6f55-4f04-97ac-e6fb0f3a5c57)

-- Enroll 'Alice Smith' (assume her student_id is 1) in 'Introduction to SQL' (assume course_id is 1) and 'Database Design' (assume course_id is 2).

university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 1, 'A');
INSERT 0 1
university_db=> INSERT INTO enrollments (student_id, course_id) VALUES (1, 2);
INSERT 0 1

![image](https://github.com/user-attachments/assets/edfc0f66-a681-4d3f-996e-da9e07dbd7fa)


-- Enroll 'Robert Johnson' (assume student_id is 2) in 'Introduction to SQL' (course_id 1).


university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (2, 1, 'B');
INSERT 0 1
university_db=> SELECT * FROM enrollments
university_db-> ;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
             3 |          1 |         1 | 2025-05-30      | A
             4 |          1 |         2 | 2025-05-30      |
             5 |          2 |         1 | 2025-05-30      | B
(3 rows)

![image](https://github.com/user-attachments/assets/62923059-f20e-4b17-91a9-469fc76d68d6)






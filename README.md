
C:\Users\Minfy>psql -U postgres
Password for user postgres:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

postgres=# DROP OWNED BY university_admin;
DROP OWNED
postgres=# CREATE USER keerthikelam WITH PASSWORD '*************';
ERROR:  role "keerthikelam" already exists
postgres=# CREATE DATABASE university_db OWNER university_admin;
CREATE DATABASE
postgres=# CREATE DATABASE minfy_db OWNER keerthikelam;
CREATE DATABASE
postgres=# GRANT ALL PRIVILEGES ON DATABASE minfy_db TO keerthikelam;
GRANT
postgres=# psql -U keerthikelam -d minfy_db
postgres-# CREATE DATABASE university_db OWNER keerthikelam;
ERROR:  syntax error at or near "psql"
LINE 1: psql -U keerthikelam -d minfy_db
        ^
postgres=# psql -U keerthikelam -d university_db
postgres-# CREATE DATABASE university_db OWNER keerthikelam;
ERROR:  syntax error at or near "psql"
LINE 1: psql -U keerthikelam -d university_db
        ^
postgres=# \u
invalid command \u
Try \? for help.
postgres=# \U
invalid command \U
Try \? for help.
postgres=# \\q
invalid command \
Try \? for help.
postgres=# \q

C:\Users\Minfy>psql -U postgres
Password for user postgres:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

postgres=# CREATE DATABASE university_db OWNER keerthikelam;
CREATE DATABASE
postgres=# psql -U keerthikelam -d university_db
postgres-# \q

C:\Users\Minfy>\l
'\l' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\Minfy>psql -U postgres
Password for user postgres:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

postgres=# \l
                                                                    List of databases
     Name      |    Owner     | Encoding | Locale Provider |      Collate       |       Ctype        | Locale | ICU Rules |       Access privileges
---------------+--------------+----------+-----------------+--------------------+--------------------+--------+-----------+-------------------------------
 minfy_db      | keerthikelam | UTF8     | libc            | English_India.1252 | English_India.1252 |        |           | =Tc/keerthikelam             +
               |              |          |                 |                    |                    |        |           | keerthikelam=CTc/keerthikelam
 postgres      | postgres     | UTF8     | libc            | English_India.1252 | English_India.1252 |        |           |
 template0     | postgres     | UTF8     | libc            | English_India.1252 | English_India.1252 |        |           | =c/postgres                  +
               |              |          |                 |                    |                    |        |           | postgres=CTc/postgres
 template1     | postgres     | UTF8     | libc            | English_India.1252 | English_India.1252 |        |           | =c/postgres                  +
               |              |          |                 |                    |                    |        |           | postgres=CTc/postgres
 university_db | keerthikelam | UTF8     | libc            | English_India.1252 | English_India.1252 |        |           |
(5 rows)


postgres=# \c university_db
You are now connected to database "university_db" as user "postgres".
university_db=# \conninfo
You are connected to database "university_db" as user "postgres" on host "localhost" (address "::1") at port "5432".
university_db=# \c university_db
You are now connected to database "university_db" as user "postgres".
university_db=# CREATE TABLE students (
university_db(#     student_id INTEGER,
university_db(#     first_name VARCHAR(50),
university_db(#     last_name VARCHAR(50),
university_db(#     email VARCHAR(100),
university_db(#     date_of_birth DATE
university_db(# );
CREATE TABLE
university_db=# \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | postgres
(1 row)


university_db=# psql -U keerthikelam -d university_db
university_db-# \c university_db
You are now connected to database "university_db" as user "postgres".
university_db-# CREATE TABLE students (
university_db(#     student_id INTEGER,
university_db(#     first_name VARCHAR(50),
university_db(#     last_name VARCHAR(50),
university_db(#     email VARCHAR(100),
university_db(#     date_of_birth DATE
university_db(# );
ERROR:  syntax error at or near "psql"
LINE 1: psql -U keerthikelam -d university_db
        ^
university_db=# CREATE TABLE students (
university_db(#     student_id INTEGER,
university_db(#     first_name VARCHAR(50),
university_db(#     last_name VARCHAR(50),
university_db(#     email VARCHAR(100),
university_db(#     date_of_birth DATE
university_db(# );
ERROR:  relation "students" already exists
university_db=#
university_db=# \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | postgres
(1 row)


university_db=#
university_db=# cd ..
university_db-# CREATE DATABASE university_db OWNER keerthikelam;
ERROR:  syntax error at or near "cd"
LINE 1: cd ..
        ^
university_db=#
university_db=# CREATE DATABASE university_db OWNER keerthikelam;
ERROR:  database "university_db" already exists
university_db=# \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | postgres
(1 row)


university_db=# \D
invalid command \D
Try \? for help.
university_db=# \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | postgres
(1 row)


university_db=# \q

C:\Users\Minfy>psql -U keerthikelam -d university_db
Password for user keerthikelam:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> \d
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | students | table | postgres
(1 row)


university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50),
university_db(>     last_name VARCHAR(50),
university_db(>     email VARCHAR(100),
university_db(>     date_of_birth DATE
university_db(> );
ERROR:  relation "students" already exists
university_db=> CREATE TABLE student (
university_db(>     first_name VARCHAR(50),
university_db(>     last_name VARCHAR(50),
university_db(>     email VARCHAR(100),
university_db(>     date_of_birth DATE
university_db(> );
CREATE TABLE
university_db=> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | student  | table | keerthikelam
 public | students | table | postgres
(2 rows)


university_db=> DROP TABLE students
university_db-> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | student  | table | keerthikelam
 public | students | table | postgres
(2 rows)


university_db-> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | student  | table | keerthikelam
 public | students | table | postgres
(2 rows)


university_db-> cls
university_db->
university_db->
university_db->
university_db->
university_db->
university_db-> \q

C:\Users\Minfy>psql -U postgres
Password for user postgres:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

postgres=# DROP TABLE students;
ERROR:  table "students" does not exist
postgres=# \d
Did not find any relations.
postgres=# \q

C:\Users\Minfy>psql -U keerthikelam -d university_admin
Password for user keerthikelam:
psql: error: connection to server at "localhost" (::1), port 5432 failed: FATAL:  database "university_admin" does not exist

C:\Users\Minfy>psql -U keerthikelam -d university_admin
Password for user keerthikelam:
psql: error: connection to server at "localhost" (::1), port 5432 failed: FATAL:  database "university_admin" does not exist

C:\Users\Minfy>psql -U keerthikelam -d university_admin
Password for user keerthikelam:
psql: error: connection to server at "localhost" (::1), port 5432 failed: FATAL:  database "university_admin" does not exist

C:\Users\Minfy>psql -U keerthikelam -d university_db
Password for user keerthikelam:
psql: error: connection to server at "localhost" (::1), port 5432 failed: FATAL:  password authentication failed for user "keerthikelam"

C:\Users\Minfy>psql -U keerthikelam -d university_db
Password for user keerthikelam:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> DROP TABLE students;
DROP TABLE
university_db=> \d
            List of relations
 Schema |  Name   | Type  |    Owner
--------+---------+-------+--------------
 public | student | table | keerthikelam
(1 row)


university_db=> cls
university_db-> clear
university_db-> DROP TABLE student
university_db-> DROP TABLE student
university_db->
university_db->
university_db->
university_db->
university_db->
university_db-> DROP TABLE student;
ERROR:  syntax error at or near "cls"
LINE 1: cls
        ^
university_db=> DROP TABLE student;;
DROP TABLE
university_db=> \d
Did not find any relations.
university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50),
university_db(>     last_name VARCHAR(50),
university_db(>     email VARCHAR(100),
university_db(>     date_of_birth DATE
university_db(> );
CREATE TABLE
university_db=> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | students | table | keerthikelam
(1 row)


university_db=> ALTER TABLE students ADD COLUMN enrollment_date DATE;
ALTER TABLE
university_db=> ALTER TABLE students ADD COLUMN enrollment_date DATE;
ERROR:  column "enrollment_date" of relation "students" already exists
university_db=> ALTER TABLE students DROP COLUMN enrollment_date;
ALTER TABLE
university_db=> ALTER TABLE students ALTER COLUMN email TYPE VARCHAR(150);
ALTER TABLE
university_db=> ALTER TABLE students RENAME COLUMN date_of_birth TO dob;
ALTER TABLE
university_db=> ALTER TABLE students ADD CONSTRAINT unique_email UNIQUE (email);
ALTER TABLE
university_db=> ALTER TABLE students RENAME TO learners;
ALTER TABLE
university_db=> ALTER TABLE learners RENAME TO students; -- Change it back
ALTER TABLE
university_db=> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | students | table | keerthikelam
(1 row)


university_db=> ALTER TABLE students ADD COLUMN phone_number VARCHAR(20);
ALTER TABLE
university_db=> ALTER TABLE students DROP COLUMN phone_number;
ALTER TABLE
university_db=> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | students | table | keerthikelam
(1 row)


university_db=> DROP TABLE IF EXISTS students
university_db-> ;
DROP TABLE
university_db=> \d
Did not find any relations.
university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50),
university_db(>     last_name VARCHAR(50),
university_db(>     email VARCHAR(100),
university_db(>     date_of_birth DATE
university_db(> );
CREATE TABLE
university_db=> ALTER TABLE students ADD COLUMN enrollment_date DATE;
ALTER TABLE
university_db=> ALTER TABLE students DROP COLUMN enrollment_date;
ALTER TABLE
university_db=> ALTER TABLE students ALTER COLUMN email TYPE VARCHAR(150);
ALTER TABLE
university_db=> ALTER TABLE students RENAME COLUMN date_of_birth TO dob;
ALTER TABLE
university_db=> ALTER TABLE students ADD CONSTRAINT unique_email UNIQUE (email);
ALTER TABLE
university_db=> ALTER TABLE students RENAME TO learners;
ALTER TABLE
university_db=> ALTER TABLE learners RENAME TO students; -- Change it back
ALTER TABLE
university_db=> \d
            List of relations
 Schema |   Name   | Type  |    Owner
--------+----------+-------+--------------
 public | students | table | keerthikelam
(1 row)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (1, 'Alice', 'Smith', 'alice.smith@example.com', '2003-05-15');
INSERT 0 1
university_db=> \d students
                       Table "public.students"
   Column   |          Type          | Collation | Nullable | Default
------------+------------------------+-----------+----------+---------
 student_id | integer                |           |          |
 first_name | character varying(50)  |           |          |
 last_name  | character varying(50)  |           |          |
 email      | character varying(150) |           |          |
 dob        | date                   |           |          |
Indexes:
    "unique_email" UNIQUE CONSTRAINT, btree (email)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (2, 'Bob', 'Johnson', 'bob.johnson@example.com', '2002-08-22'),
university_db->        (3, 'Charlie', 'Brown', 'charlie.brown@example.com', '2003-01-10');
INSERT 0 2
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (4, 'Keerthi', 'Kelam', 'keerhti.kelam@example.com', '2004-06-28'),
university_db-> VALUES (5, 'Meghana sai', 'Bhima', 'meghanasai@example.com', '2003-12-22');
ERROR:  syntax error at or near "VALUES"
LINE 3: VALUES (5, 'Meghana sai', 'Bhima', 'meghanasai@example.com',...
        ^
university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (4, 'Keerthi', 'Kelam', 'keerhti.kelam@example.com', '2004-06-28'),
university_db->        (5, 'Meghana sai', 'Bhima', 'meghanasai@example.com', '2003-12-22');
INSERT 0 2
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(5 rows)


university_db=> SELECT first_name, last_name, email FROM students;
 first_name  | last_name |           email
-------------+-----------+---------------------------
 Alice       | Smith     | alice.smith@example.com
 Bob         | Johnson   | bob.johnson@example.com
 Charlie     | Brown     | charlie.brown@example.com
 Keerthi     | Kelam     | keerhti.kelam@example.com
 Meghana sai | Bhima     | meghanasai@example.com
(5 rows)


university_db=> SELECT * FROM students WHERE first_name = "Alice";
ERROR:  column "Alice" does not exist
LINE 1: SELECT * FROM students WHERE first_name = "Alice";
                                                  ^
university_db=> SELECT * FROM students WHERE first_name = 'Alice';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> SELECT * FROM students WHERE student_id = 1;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> SELECT first_name, last_name FROM students WHERE last_name = 'Smith';
 first_name | last_name
------------+-----------
 Alice      | Smith
(1 row)


university_db=> SELECT * FROM students WHERE dob >= '2004-06-28';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          4 | Keerthi    | Kelam     | keerhti.kelam@example.com | 2004-06-28
(1 row)


university_db=> SELECT * FROM students WHERE dob BETWEEN '2002-02-01' AND '2002-11-31';
ERROR:  date/time field value out of range: "2002-11-31"
LINE 1: ... FROM students WHERE dob BETWEEN '2002-02-01' AND '2002-11-3...
                                                             ^
university_db=> SELECT * FROM students WHERE dob BETWEEN '2002-01-01' AND '1995-12-31';
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> SELECT * FROM students WHERE first_name LIKE 'A%';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (6, 'Anil);
university_db'>
university_db'> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db'> VALUES (6, 'Anil');
university_db'> ;
university_db'> ;;
university_db'> exit
Use control-C to quit.
university_db'> \q

C:\Users\Minfy>psql -U keerthikelam -d university_db
Password for user keerthikelam:
psql: error: connection to server at "localhost" (::1), port 5432 failed: FATAL:  password authentication failed for user "keerthikelam"

C:\Users\Minfy>psql -U keerthikelam -d university_db
Password for user keerthikelam:
psql (17.5)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (6, 'anil');
ERROR:  INSERT has more target columns than expressions
LINE 1: INSERT INTO students (student_id, first_name, last_name, ema...
                                                      ^
university_db=> INSERT INTO students (student_id, first_name)
university_db-> VALUES (6, 'anil');
INSERT 0 1
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
(6 rows)


university_db=> SELECT * FROM students WHERE first_name LIKE 'A%';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> SELECT * FROM students WHERE first_name ILIKE 'A%';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
          6 | anil       |           |                         |
(2 rows)


university_db=> SELECT * FROM students WHERE email ILIKE '%.com';
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(5 rows)


university_db=> SELECT * FROM students WHERE first_name = 'Alice' AND last_name = 'Smith';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15
(1 row)


university_db=> SELECT * FROM students WHERE student_id = 1 OR student_id = 3;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          1 | Alice      | Smith     | alice.smith@example.com   | 2003-05-15
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(2 rows)


university_db=> SELECT * FROM students WHERE student_id IN (1, 3, 5);
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(3 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, dob) VALUES (4, 'Diana', 'Prince', '2001-11-01');
INSERT 0 1
university_db=>
university_db=> SELECT * FROM students WHERE email IS NULL;
 student_id | first_name | last_name | email |    dob
------------+------------+-----------+-------+------------
          6 | anil       |           |       |
          4 | Diana      | Prince    |       | 2001-11-01
(2 rows)


university_db=>
university_db=> SELECT * FROM students WHERE email IS NOT NULL;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(5 rows)


university_db=> SELECT * FROM students WHERE student_id = 2.33;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> SELECT * FROM students WHERE student_id = 2;
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com | 2002-08-22
(1 row)


university_db=> SELECT * FROM students WHERE dob < '2003-01-2003'
university_db-> SELECT * FROM students WHERE dob < '2003-01-01'
university_db-> ;
ERROR:  syntax error at or near "SELECT"
LINE 2: SELECT * FROM students WHERE dob < '2003-01-01'
        ^
university_db=> SELECT * FROM students WHERE dob < '2003-01-01';
 student_id | first_name | last_name |          email          |    dob
------------+------------+-----------+-------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com | 2002-08-22
          4 | Diana      | Prince    |                         | 2001-11-01
(2 rows)


university_db=> SELECT * FROM students WHERE dob LIKE 'B%' OR dob LIKE '%c;
university_db'> ;
university_db'> ';
ERROR:  operator does not exist: date ~~ unknown
LINE 1: SELECT * FROM students WHERE dob LIKE 'B%' OR dob LIKE '%c;
                                         ^
HINT:  No operator matches the given name and argument types. You might need to add explicit type casts.
university_db=> SELECT * FROM students WHERE dob LIKE 'B%' OR dob LIKE '%C';
ERROR:  operator does not exist: date ~~ unknown
LINE 1: SELECT * FROM students WHERE dob LIKE 'B%' OR dob LIKE '%C';
                                         ^
HINT:  No operator matches the given name and argument types. You might need to add explicit type casts.
university_db=> SELECT * FROM students WHERE first_name LIKE '%B' OR first_name LIKE '%C';
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> SELECT * FROM students WHERE first_name LIKE 'B%' OR first_name LIKE 'C%';
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-01-10
(2 rows)


university_db=> SELECT * FROM students WHERE email LIKE '%example.com';
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(5 rows)


university_db=> SELECT * FROM students WHERE email IS NULL;
 student_id | first_name | last_name | email |    dob
------------+------------+-----------+-------+------------
          6 | anil       |           |       |
          4 | Diana      | Prince    |       | 2001-11-01
(2 rows)


university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
          4 | Diana       | Prince    |                           | 2001-11-01
(7 rows)


university_db=> UPDATE students
university_db-> SET email = 'keerthi.kelam@example.net'
university_db-> WHERE student_id = 4;
ERROR:  duplicate key value violates unique constraint "unique_email"
DETAIL:  Key (email)=(keerthi.kelam@example.net) already exists.
university_db=> UPDATE students
university_db-> SET email = 'keerthi.kelam@example.nets'
university_db-> WHERE student_id = 4;
ERROR:  duplicate key value violates unique constraint "unique_email"
DETAIL:  Key (email)=(keerthi.kelam@example.nets) already exists.
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
          4 | Diana       | Prince    |                           | 2001-11-01
(7 rows)


university_db=> UPDATE students
university_db-> SET email = 'diana.prince@example.net'
university_db-> WHERE student_id = 4;
ERROR:  duplicate key value violates unique constraint "unique_email"
DETAIL:  Key (email)=(diana.prince@example.net) already exists.
university_db=> UPDATE students
university_db-> SET email = 'keerthi.kelam@example.nets'
university_db-> UPDATE students
university_db-> SET first_name = 'Diana'
university_db-> SET first_name = 'Diana'
university_db-> ;
ERROR:  syntax error at or near "UPDATE"
LINE 3: UPDATE students
        ^
university_db=> UPDATE students
university_db-> SET student_id = 7
university_db-> WHERE first_name = 'Diana';
UPDATE 1
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2003-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
          7 | Diana       | Prince    |                           | 2001-11-01
(7 rows)


university_db=> UPDATE students
university_db-> SET email = 'diana.prince@example.net'
university_db-> WHERE student_id = 7;
UPDATE 1
university_db=> UPDATE students
university_db-> SET dob = '2002-05-15'
university_db-> WHERE student_id = 1;
UPDATE 1
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
          7 | Diana       | Prince    | diana.prince@example.net  | 2001-11-01
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
(7 rows)


university_db=> UPDATE students
university_db-> SET dob = '2003-02-15'
university_db-> WHERE student_id = 4;
UPDATE 1
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-01-10
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          6 | anil        |           |                           |
          7 | Diana       | Prince    | diana.prince@example.net  | 2001-11-01
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2003-02-15
(7 rows)


university_db=> UPDATE students
university_db-> SET dob = '2004-06-28'
university_db-> WHERE student_id = 4;
UPDATE 1
university_db=> UPDATE students
university_db-> SET dob = '2002-05-15'
university_db-> WHERE student_id = ;
ERROR:  syntax error at or near ";"
LINE 3: WHERE student_id = ;
                           ^
university_db=> UPDATE students
university_db-> SET dob = '2003-02-15'
university_db-> WHERE first_name = 'Charlie';
UPDATE 1
university_db=> UPDATE students
university_db-> SET email = 'diana.prince@example.org'
university_db-> WHERE student_id = 7;
UPDATE 1
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
(7 rows)


university_db=> INSERT INTO students (student_id, first_name, last_name, email, dob)
university_db-> VALUES (99, 'Temp', 'User', 'temp@example.com', '2000-01-01');
INSERT 0 1
university_db=> SELECT * FROM students WHERE student_id = 99;
 student_id | first_name | last_name |      email       |    dob
------------+------------+-----------+------------------+------------
         99 | Temp       | User      | temp@example.com | 2000-01-01
(1 row)


university_db=> DELETE FROM students WHERE student_id = 99;
DELETE 1
university_db=> SELECT * FROM students WHERE student_id = 99;
 student_id | first_name | last_name | email | dob
------------+------------+-----------+-------+-----
(0 rows)


university_db=> SELECT * FROM students ORDER BY last_name ASC;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          6 | anil        |           |                           |
(7 rows)


university_db=> SELECT * FROM students ORDER BY last_name ASC;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          6 | anil        |           |                           |
(7 rows)


university_db=> SELECT * FROM students ORDER BY first_name ASC;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          6 | anil        |           |                           |
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(7 rows)


university_db=> SELECT * FROM students ORDER BY dob DESC;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          6 | anil        |           |                           |
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
(7 rows)


university_db=> SELECT * FROM students ORDER BY first_name, last_name;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          6 | anil        |           |                           |
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(7 rows)


university_db=> SELECT * FROM students ORDER BY dob ASC;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          6 | anil        |           |                           |
(7 rows)


university_db=> SELECT * FROM students ORDER BY last_name DESC, first_name ASC;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          6 | anil        |           |                           |
          1 | Alice       | Smith     | alice.smith@example.com   | 2002-05-15
          7 | Diana       | Prince    | diana.prince@example.org  | 2001-11-01
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          2 | Bob         | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(7 rows)


university_db=> SELECT * FROM students ORDER BY dob DESC LIMIT 3;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          6 | anil        |           |                           |
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(3 rows)


university_db=> SELECT * FROM students ORDER BY student_id LIMIT 3 OFFSET 2;
 student_id | first_name  | last_name |           email           |    dob
------------+-------------+-----------+---------------------------+------------
          3 | Charlie     | Brown     | charlie.brown@example.com | 2003-02-15
          4 | Keerthi     | Kelam     | keerhti.kelam@example.com | 2004-06-28
          5 | Meghana sai | Bhima     | meghanasai@example.com    | 2003-12-22
(3 rows)


university_db=> SELECT * FROM students ORDER BY student_id LIMIT 2 OFFSET 2;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-02-15
          4 | Keerthi    | Kelam     | keerhti.kelam@example.com | 2004-06-28
(2 rows)


university_db=> SELECT * FROM students dob DESC LIMIT 2;
ERROR:  syntax error at or near "DESC"
LINE 1: SELECT * FROM students dob DESC LIMIT 2;
                                   ^
university_db=> SELECT * FROM students ORDER BY dob DESC LIMIT 2;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          6 | anil       |           |                           |
          4 | Keerthi    | Kelam     | keerhti.kelam@example.com | 2004-06-28
(2 rows)


university_db=> SELECT * FROM students ORDER BY dob ASC LIMIT 2;
 student_id | first_name | last_name |          email           |    dob
------------+------------+-----------+--------------------------+------------
          7 | Diana      | Prince    | diana.prince@example.org | 2001-11-01
          1 | Alice      | Smith     | alice.smith@example.com  | 2002-05-15
(2 rows)


university_db=> SELECT * FROM students ORDER BY student_id ASC LIMIT 2 OFFSET 1;
 student_id | first_name | last_name |           email           |    dob
------------+------------+-----------+---------------------------+------------
          2 | Bob        | Johnson   | bob.johnson@example.com   | 2002-08-22
          3 | Charlie    | Brown     | charlie.brown@example.com | 2003-02-15
(2 rows)


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


university_db=> SELECT DISTINCT EXTRACT(YEAR FROM dob) AS birth_years FROM students ORDER BY dob;
ERROR:  for SELECT DISTINCT, ORDER BY expressions must appear in select list
LINE 1: ...CT(YEAR FROM dob) AS birth_years FROM students ORDER BY dob;
                                                                   ^
university_db=> SELECT DISTINCT EXTRACT(YEAR FROM dob) AS birth_years FROM students ORDER BY birth_years;
 birth_years
-------------
        2001
        2002
        2003
        2004

(5 rows)


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


university_db=> SELECT COUNT(*) AS total_students FROM students;
 total_students
----------------
              8
(1 row)


university_db=> SELECT MIN(dob) AS oldest_student_dob FROM students;
 oldest_student_dob
--------------------
 2001-11-01
(1 row)


university_db=> SELECT COUNT(DISTINCT last_name) AS unique_last_names FROM students;
 unique_last_names
-------------------
                 6
(1 row)


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


university_db=> SELECT COUNT(*)
university_db-> ;
 count
-------
     1
(1 row)


university_db=> SELECT COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY last_name
university_db-> ORDER BY number_of_students DESC;
 number_of_students
--------------------
                  2
                  1
                  1
                  1
                  1
                  1
                  1
(7 rows)


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


university_db=> SELECT fisrt_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY last_name
university_db-> ORDER BY number_of_students DESC;
ERROR:  column "fisrt_name" does not exist
LINE 1: SELECT fisrt_name, COUNT(*) AS number_of_students
               ^
HINT:  Perhaps you meant to reference the column "students.first_name".
university_db=> SELECT last_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY first_name
university_db-> ORDER BY number_of_students DESC;
ERROR:  column "students.last_name" must appear in the GROUP BY clause or be used in an aggregate function
LINE 1: SELECT last_name, COUNT(*) AS number_of_students
               ^
university_db=> SELECT fisrt_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY first_name
university_db-> ORDER BY number_of_students DESC;
ERROR:  column "fisrt_name" does not exist
LINE 1: SELECT fisrt_name, COUNT(*) AS number_of_students
               ^
HINT:  Perhaps you meant to reference the column "students.first_name".
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


university_db=> SELECT EXTRACT(YEAR FROM dob) AS birth_years
university_db-> ;
ERROR:  column "dob" does not exist
LINE 1: SELECT EXTRACT(YEAR FROM dob) AS birth_years
                                 ^
university_db=> SELECT first_name, EXTRACT(YEAR FROM dob) AS birth_years
university_db-> FROM students
university_db-> GROUP BY birth_years
university_db-> ;
ERROR:  column "students.first_name" must appear in the GROUP BY clause or be used in an aggregate function
LINE 1: SELECT first_name, EXTRACT(YEAR FROM dob) AS birth_years
               ^
university_db=> SELECT first_name, EXTRACT(YEAR FROM dob) AS birth_years
university_db-> FROM students
university_db-> GROUP BY birth_years, first_name;
 first_name  | birth_years
-------------+-------------
 anil        |
 Charlie     |        2003
 Alice       |        2002
 Meghana sai |        2003
 Eve         |        2004
 Diana       |        2001
 Bob         |        2002
 Keerthi     |        2004
(8 rows)


university_db=> SELECT EXTRACT(YEAR FROM dob) AS birth_years, COUNT(EXTRACT(YEAR FROM dob)) AS count
university_db-> FROM students
university_db-> GROUP BY birth_years;
 birth_years | count
-------------+-------
             |     0
        2003 |     2
        2002 |     2
        2001 |     1
        2004 |     2
(5 rows)


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


university_db=> SELECT last_name, COUNT(*) AS number_of_students
university_db-> FROM students
university_db-> GROUP BY last_name
university_db-> HAVING COUNT(*) > 1
university_db-> ORDER BY number_of_students DESC;
 last_name | number_of_students
-----------+--------------------
 Smith     |                  2
(1 row)


university_db=> SELECT EXTRACT(YEAR FROM dob) AS birth_year, COUNT(*) AS students_in_year
university_db-> FROM students
university_db-> WHERE dob IS NOT NULL
university_db-> GROUP BY birth_year
university_db-> ORDER BY birth_year;
 birth_year | students_in_year
------------+------------------
       2001 |                1
       2002 |                2
       2003 |                2
       2004 |                2
(4 rows)


university_db=> DROP TABLE students;
DROP TABLE
university_db=> SELECT * FROM students;
ERROR:  relation "students" does not exist
LINE 1: SELECT * FROM students;
                      ^
university_db=> DROP TABLE IF EXISTS students; -- Start fresh for constraint examples
NOTICE:  table "students" does not exist, skipping
DROP TABLE
university_db=> CREATE TABLE students (
university_db(>     student_id INTEGER,
university_db(>     first_name VARCHAR(50) NOT NULL, -- first_name cannot be NULL
university_db(>     last_name VARCHAR(50) NOT NULL,
university_db(>     email VARCHAR(100) UNIQUE,      -- email must be unique (and can be NULL by default for UNIQUE)
university_db(>     dob DATE,
university_db(>     enrollment_status VARCHAR(10) CHECK (enrollment_status IN ('enrolled', 'graduated', 'dropped'))
university_db(> );
CREATE TABLE
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


university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charlie', 'Brown', '2003-01-10', 'pending');
ERROR:  INSERT has more target columns than expressions
LINE 1: ...INTO students (first_name, last_name, email, dob, enrollment...
                                                             ^
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


university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charliechar', 'BrownBear', 'charlie.brown@example.com', '2003-01-10', 'pending');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(charlie.brown@example.com) already exists.
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charliechar', 'BrownBear', 'charlie.brown@example.com', '2003-01-10');
ERROR:  INSERT has more target columns than expressions
LINE 1: ...INTO students (first_name, last_name, email, dob, enrollment...
                                                             ^
university_db=> INSERT INTO students (last_name, email, dob, enrollment_status)
university_db-> VALUES ('BrownBear', 'charlie.brown@example.com', '2003-01-10');
ERROR:  INSERT has more target columns than expressions
LINE 1: INSERT INTO students (last_name, email, dob, enrollment_stat...
                                                     ^
university_db=> INSERT INTO students (last_name, email, dob, enrollment_status)
university_db-> VALUES ('BrownBear', 'charlie.brown@example.com', '2003-01-10', 'pending');
ERROR:  null value in column "first_name" of relation "students" violates not-null constraint
DETAIL:  Failing row contains (6, null, BrownBear, charlie.brown@example.com, 2003-01-10, pending).
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charliechar', 'BrownBear', 'charlie.brown@example.com', '2003-01-10', 'pending');
ERROR:  duplicate key value violates unique constraint "students_email_key"
DETAIL:  Key (email)=(charlie.brown@example.com) already exists.
university_db=> INSERT INTO students (first_name, last_name, email, dob, enrollment_status)
university_db-> VALUES ('Charliechar', 'BrownBear', 'ccharlie.brown@example.com', '2003-01-10', 'pending');
INSERT 0 1
university_db=> SELECT * FROM students;
 student_id | first_name  | last_name |           email            |    dob     | enrollment_status
------------+-------------+-----------+----------------------------+------------+-------------------
          1 | Alice       | Smith     | alice.smith@example.com    | 2003-05-15 | enrolled
          2 | Robert      | Johnson   | robert.j@example.com       | 2002-08-22 | enrolled
          3 | Charlie     | Brown     | charlie.brown@example.com  | 2003-01-10 | pending
          4 | Sai         | Brown     |                            | 2003-01-10 | pending
          8 | Charliechar | BrownBear | ccharlie.brown@example.com | 2003-01-10 | pending
(5 rows)


university_db=> CREATE TABLE courses (
university_db(>     course_id SERIAL PRIMARY KEY,
university_db(>     course_name VARCHAR(100) NOT NULL UNIQUE,
university_db(>     credits INTEGER CHECK (credits > 0 AND credits < 10) -- Example of CHECK
university_db(> );
CREATE TABLE
university_db=> DROP TABLE courses;
DROP TABLE
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


university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (999, 1, 'A');
ERROR:  insert or update on table "enrollments" violates foreign key constraint "fk_student"
DETAIL:  Key (student_id)=(999) is not present in table "students".
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 90, 'A');
ERROR:  insert or update on table "enrollments" violates foreign key constraint "fk_course"
DETAIL:  Key (course_id)=(90) is not present in table "courses".
university_db=> INSERT INTO enrollments (student_id, course_id, grade) VALUES (1, 1, 'A');
INSERT 0 1
university_db=> INSERT INTO enrollments (student_id, course_id) VALUES (1, 2);
INSERT 0 1
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


university_db=> SELECT * FROM students WHERE student_id = 1;
 student_id | first_name | last_name |          email          |    dob     | enrollment_status
------------+------------+-----------+-------------------------+------------+-------------------
          1 | Alice      | Smith     | alice.smith@example.com | 2003-05-15 | enrolled
(1 row)


university_db=> SELECT * FROM enrollments WHERE student_id = 1;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
             3 |          1 |         1 | 2025-05-30      | A
             4 |          1 |         2 | 2025-05-30      |
(2 rows)


university_db=> DELETE FROM students WHERE student_id = 1;
DELETE 1
university_db=> SELECT * FROM students WHERE student_id = 1;
 student_id | first_name | last_name | email | dob | enrollment_status
------------+------------+-----------+-------+-----+-------------------
(0 rows)


university_db=> SELECT * FROM enrollments WHERE student_id = 1;
 enrollment_id | student_id | course_id | enrollment_date | grade
---------------+------------+-----------+-----------------+-------
(0 rows)


university_db=>

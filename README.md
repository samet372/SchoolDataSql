# SchoolDataSql
PostgreSQL codes for school management system
-----------------------------------------------
CREATE TABLE students ( <br>
    student_id SERIAL PRIMARY KEY,<br>
    student_number VARCHAR(20) UNIQUE NOT NULL,<br>
    student_name VARCHAR(100) NOT NULL,<br>
    student_surname VARCHAR(100) NOT NULL<br>
);<br>
<br>
CREATE TABLE courses (<br>
    course_code VARCHAR(20) PRIMARY KEY,<br>
    course_name VARCHAR(100) NOT NULL<br>
);<br>
<br>
CREATE TABLE grades (<br>
    student_id INTEGER REFERENCES students(student_id),<br>
    course_code VARCHAR(20) REFERENCES courses(course_code),<br>
    grade NUMERIC(3, 2) NOT NULL,<br>
    PRIMARY KEY (student_id, course_code)<br>
);<br>

-----------------------------------------------

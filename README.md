# SchoolDataSql
PostgreSQL codes for school management system
-----------------------------------------------
CREATE TABLE students ( /br
    student_id SERIAL PRIMARY KEY,
    student_number VARCHAR(20) UNIQUE NOT NULL,
    student_name VARCHAR(100) NOT NULL,
	student_surname VARCHAR(100) NOT NULL
);

CREATE TABLE courses (
    course_code VARCHAR(20) PRIMARY KEY,
    course_name VARCHAR(100) NOT NULL
);

CREATE TABLE grades (
    student_id INTEGER REFERENCES students(student_id),
    course_code VARCHAR(20) REFERENCES courses(course_code),
    grade NUMERIC(3, 2) NOT NULL,
    PRIMARY KEY (student_id, course_code)
);

-----------------------------------------------

# TECLMS-TECMIS System
***

<p>This project is part of an assignment to build a basic a Student Management System designed for the Faculty of Technology. It allows administrators, deans, lecturers, technical officers, and students to manage and view student details, course information, attendance, and exam results.</p>

### 🤖 Project Overview

- Student details, including proper and repeat students
- Course units data
- Attendance tracking for both theory and practical sessions
- Marks recording for assessments, quizzes, mid-semester exams, and final exams
- Eligibility checking based on attendance and continuous assessment (CA) marks
- Grading system based on faculty bylaws
- Viewing student grades, SGPA, and CGPA

***

# SQL Table Structure

This repository contains the SQL table structure for a TECLMS-TECMIS System. The database consists of few tables: `Students`, `lecture`, `Course`, `Mark`, `user`,`Admin`,`Mark`,`Medical`,`Dean`,`Attendence`,`Notice` and `Department`,

## Table Definitions

### User

The `User` table stores information about all Users Details.

| Field   | Type        | Null | Key | Default |
|---------|-------------|------|-----|---------|
| nic     | char(12)    | NO   | PRI | NULL    |
| f_name  | varchar(10) | YES  |     | NULL    |
| l_name  | varchar(10) | YES  |     | NULL    |
| address | varchar(15) | YES  |     | NULL    |
| email   | varchar(15) | YES  |     | NULL    |
| gender  | varchar(5)  | YES  |     | NULL    |
| bod     | date        | YES  |     | NULL    |

### Dean

The `Dean` table stores information about Dean of Our Faculty.

| Field   | Type     | Null | Key | Default | Extra |
|---------|----------|------|-----|---------|-------|
| dean_id | char(5)  | NO   | PRI | NULL    |       |
| nic     | char(12) | YES  | MUL | NULL    |       |

### Students

The `Students` table stores information about the students.

| Field      | Data Type   | Null | Key | Default |
|------------|-------------|------|-----|---------|
| student_id | varchar(6)  | NO   | PRI | NULL    |
| nic        | char(12)    | YES  | MUL | NULL    |
| state      | varchar(30) | YES  |     | NULL    |
| dep_id     | char(4)     | YES  | MUL | NULL    |

### Admin

The `Admin` table store information about admin data. 

| Field    | Type        | Null | Key | Default | 
|----------|-------------|------|-----|---------|
| nic      | char(12)    | YES  | MUL | NULL    |       
| admin_id | varchar(10) | NO   | PRI | NULL    |       
| role     | varchar(10) | YES  |     | NULL    |  

### Mark

The `Mark` table stores marks of the all student .

| Field         | Type       | Null | Key | Default | 
|---------------|------------|------|-----|---------|
| mark_id       | char(10)   | NO   | PRI | NULL    |       
| quiz_1        | int(11)    | YES  |     | NULL    |       
| quiz_2        | int(11)    | YES  |     | NULL    |       
| quiz_3        | int(11)    | YES  |     | NULL    |       
| assesment     | int(11)    | YES  |     | NULL    |       
| mid_theory    | int(11)    | YES  |     | NULL    |       
| mid_practical | int(11)    | YES  |     | NULL    |       
| end_theory    | int(11)    | YES  |     | NULL    |       
| end_practical | int(11)    | YES  |     | NULL    |       
| student_id    | varchar(6) | YES  | MUL | NULL    |       
| course_code   | char(8)    | YES  | MUL | NULL    |       

### Medical

The `Medical` table stores about mediacal information of All Student.

| Field           | Type        | Null | Key | Default | 
|-----------------|-------------|------|-----|---------|
| medical_id      | char(10)    | NO   | PRI | NULL    |       
| description     | varchar(50) | YES  |     | NULL    |       
| s_date          | date        | YES  |     | NULL    |       
| e_date          | date        | YES  |     | NULL    |       
| student_id      | varchar(6)  | YES  | MUL | NULL    |       
| tech_officer_iD | char(10)    | YES  | MUL | NULL    |       

### Lecture

The `Lecture` table stores information about Lecture.

| Field      | Type        | Null | Key | Default |
|------------|-------------|------|-----|---------|
| lecture_id | varchar(5)  | NO   | PRI | NULL    |
| nic        | char(12)    | YES  | MUL | NULL    |
| position   | varchar(20) | YES  |     | NULL    |
| dep_id     | char(4)     | YES  | MUL | NULL    |

### Course

The `Course` table stores information about Course Details.

| Field         | Type        | Null | Key | Default |
|---------------|-------------|------|-----|---------|
| course_code   | char(8)     | NO   | PRI | NULL    |
| course_name   | varchar(20) | YES  |     | NULL    |
| course_credit | int(11)     | YES  |     | NULL    |
| course_houre  | int(11)     | YES  |     | NULL    |
| course_type   | varchar(15) | NO   |     | NULL    |
| dep_id        | char(4)     | YES  | MUL | NULL    |

### Attendence 

The `Attendence` table stores information about Attendence.

| Field           | Type        | Null | Key | Default |
|-----------------|-------------|------|-----|---------|
| date            | date        | YES  |     | NULL    |
| att_state       | varchar(20) | YES  |     | NULL    |
| session_type    | varchar(25) | YES  |     | NULL    |
| student_id      | varchar(6)  | YES  | MUL | NULL    |
| medical_id      | char(10)    | YES  | MUL | NULL    |
| tech_officer_id | varchar(6)  | YES  | MUL | NULL    |
| course_code     | char(8)     | YES  | MUL | NULL    |

### Notice

The `Notice` table stores information about Notice.

| Field       | Type        | Null | Key | Default |
|-------------|-------------|------|-----|---------|
| notice_id   | varchar(6)  | YES  |     | NULL    |
| description | varchar(30) | YES  |     | NULL    |
| date        | date        | YES  |     | NULL    |
| lecture_id  | varchar(5)  | YES  | MUL | NULL    |

### Department

The `Department` table stores information about Department.

| Field    | Type        | Null | Key | Default |
|----------|-------------|------|-----|---------|
| dep_id   | char(4)     | NO   | PRI | NULL    |
| dep_name | varchar(50) | YES  |     | NULL    |
| dean_id  | char(5)     | YES  | MUL | NULL    |
| admin_id | varchar(10) | YES  | MUL | NULL    |


Don't forget to hit the :star: if you like this repo.
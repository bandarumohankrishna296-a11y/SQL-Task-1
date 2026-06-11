Student Database Management
1.Database Setup
i). Create Database
CREATE DATABASE StudentManagement;
USE StudentManagement;
ii). Create Students Table
code:
CREATE TABLE Students (
    StudentID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(50),
    Gender VARCHAR(10),
    Age INT,
    Grade VARCHAR(5),
    MathScore INT,
    ScienceScore INT,
    EnglishScore INT
);
2. Insert Sample Data (10 Records)
INSERT INTO Students
(Name, Gender, Age, Grade, MathScore, ScienceScore, EnglishScore)
VALUES
('Rahul', 'Male', 16, 'A', 85, 90, 88),
('Priya', 'Female', 15, 'A', 92, 95, 91),
('Arjun', 'Male', 16, 'B', 78, 82, 75),
('Sneha', 'Female', 15, 'A', 89, 87, 90),
('Kiran', 'Male', 17, 'C', 65, 70, 68),
('Anjali', 'Female', 16, 'B', 80, 85, 84),
('Vikram', 'Male', 15, 'B', 88, 86, 82),
('Divya', 'Female', 17, 'A', 95, 93, 97),
('Rohit', 'Male', 16, 'C', 72, 75, 70),
('Meena', 'Female', 15, 'B', 84, 88, 86);
3.SQL Queries to Perform
i). Show All Student Details
SELECT * FROM Students;
ii)Average Score in Each Subject
SELECT
AVG(MathScore) AS Average_Math,
AVG(ScienceScore) AS Average_Science,
AVG(EnglishScore) AS Average_English
FROM Students;
iii)Top Performer (Highest Total Score)
SELECT
StudentID,
Name,
(MathScore + ScienceScore + EnglishScore) AS TotalScore
FROM Students
ORDER BY TotalScore DESC
LIMIT 1;
iv)Count Students Per Grade
SELECT Grade, COUNT(*) AS TotalStudents
FROM Students
GROUP BY Grade;
v)Average Score by Gender
SELECT
Gender,
AVG(MathScore) AS AvgMath,
AVG(ScienceScore) AS AvgScience,
AVG(EnglishScore) AS AvgEnglish
FROM Students
GROUP BY Gender;
vi)Students with Math Score Greater Than 80
SELECT *
FROM Students
WHERE MathScore > 80;
vii)Update a Student's Grade
Example: Update Rohit's grade from C to B.
UPDATE Students
SET Grade = 'B'
WHERE Name = 'Rohit';
Verify:
SELECT * FROM Students
WHERE Name = 'Rohit';

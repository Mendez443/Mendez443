#module 1: 

DECLARE
    employee_name VARCHAR2(50) := 'John Doe';
    salary NUMBER := 60000;
    hire_date DATE := DATE '2023-01-15';
BEGIN
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || employee_name);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || salary);
    DBMS_OUTPUT.PUT_LINE('Hire Date: ' || hire_date);
END;

module 2: 

DECLARE
    
    goal_hours NUMBER := 100; 
    
    current_hours NUMBER := 50; 
    
    progress_percentage NUMBER := (current_hours / goal_hours) * 100; 
BEGIN
    
    DBMS_OUTPUT.PUT_LINE('Reading Goal: ' || goal_hours || ' hours');
    DBMS_OUTPUT.PUT_LINE('Current Hours Read: ' || current_hours || ' hours');
    DBMS_OUTPUT.PUT_LINE('Progress: ' || progress_percentage || '%');

    
    IF current_hours >= goal_hours THEN
        DBMS_OUTPUT.PUT_LINE('Congratulations! You have reached your reading goal!');
    END IF;
END;


module 3:

CREATE TABLE students ( 
    student_id INT PRIMARY KEY, 
    name VARCHAR(255), 
    grade INT, 
    favorite_subject VARCHAR(50) 
)

    INSERT INTO students (student_id, name, grade, favorite_subject) VALUES 
    (1, 'Alice JohnINSERTson', 7, 'Math');
    

    INSERT INTO students (student_id, name, grade, favorite_subject) VALUES 
    (2, 'Bob SmiINSERTth', 8, 'Science');

    INSERT INTO students (student_id, name, grade, favorite_subject) VALUES 
    (2, 'Bob Smith', 8, 'Science');

    INSERT INTO students (student_id, name, grade, favorite_subject) VALUES 
    (3, 'Charlie Brown', 9, 'History');

    INSERT INTO students (student_id, name, grade, favorite_subject) VALUES 
    (4, 'Diana Jones', 10, 'English');

    INSERT INTO students (student_id, name, grade, favorite_subject) VALUES 
    (5, 'Ethan Davis', 7, 'Art');

    
SELECT * FROM students

SELECT * FROM students WHERE grade = 7

SELECT * FROM students WHERE favorite_subject = 'Math'

module 4:

CREATE TABLE games (
    game_id INT PRIMARY KEY,
    title VARCHAR(255),
    console VARCHAR(50),
    release_year INT
);

 INSERT INTO games (game_id, title, console, release_year) VALUES 
    (1, 'The Legend of Zelda: Breath of the Wild', 'Nintendo Switch', 2017);

 INSERT INTO games (game_id, title, console, release_year) VALUES 
    (2, 'Super Mario Odyssey', 'Nintendo Switch', 2017);

 INSERT INTO games (game_id, title, console, release_year) VALUES 
    (3, 'Red Dead Redemption 2', 'PlayStation 4', 2018);

 INSERT INTO games (game_id, title, console, release_year) VALUES 
    (4, 'Grand Theft Auto V', 'PlayStation 3', 2013);

 INSERT INTO games (game_id, title, console, release_year) VALUES 
    (5, 'The Witcher 3: Wild Hunt', 'PC', 2015);

    SELECT * FROM games
    SELECT * FROM games WHERE release_year > 2015
    SELECT * FROM games WHERE console = 'Nintendo Switch'

module 5:
CREATE TABLE pilipino_club ( 
    member_id INT PRIMARY KEY, 
    member_name VARCHAR(255) 
);
CREATE TABLE art_club ( 
    member_id INT PRIMARY KEY, 
    member_name VARCHAR(255) 
);
INSERT INTO pilipino_club (member_id, member_name) VALUES 
    (1, 'Maria Santos')INSERT INTO pilipino_club (member_id, member_name) VALUES 
    (2, 'Juan Dela Cruz')INSERT INTO pilipino_club (member_id, member_name) VALUES 
    (3, 'Elena Garcia')INSERT INTO art_club (member_id, member_name) VALUES 
    (1, 'Maria Santos')INSERT INTO art_club (member_id, member_name) VALUES 
    (2, 'David Lee')INSERT INTO art_club (member_id, member_name) VALUES 
    (5, 'Sarah Kim')SELECT pilipino_club.member_name 

 
FROM pilipino_club SELECT pilipino_club.member_name 
 
FROM pilipino_club 
 
LEFT JOIN art_club ON pilipino_club.member_id = art_club

 SELECT pilipino_club.member_name 
 
FROM pilipino_club 
 
 RIGHT JOIN art_club ON pilipino_club.member_id = art_club.member_id

SELECT pilipino_club.member_name 
 
FROM pilipino_club 

FULL JOIN art_club ON pilipino_club.member_id = art_club.member_id

1. PL/SQL vs. SQL
SQL (Structured Query Language): SQL is a declarative language designed for querying and manipulating data in relational databases. It focuses on what you want to achieve, not how to achieve it. Think of it as giving instructions like “Get me all customers from California.”
PL/SQL (Procedural Language/SQL): PL/SQL is an extension of SQL that adds procedural programming capabilities. It allows you to write more complex logic, including variables, control structures (like loops and conditional statements), and functions. It’s like adding a “how-to” guide to your SQL instructions.

2. Anonymous Blocks in PL/SQL
Anonymous Blocks: These are PL/SQL code blocks that are not named and are executed immediately. They are useful for short, self-contained tasks.
When to use them:
Quick calculations or data manipulation: You might use an anonymous block to perform a one-time calculation or update a few rows in a table.
Testing code snippets: You can write and execute small pieces of PL/SQL code within an anonymous block to test their functionality.

3. Common PL/SQL Data Types
   
4.Control Structures in PL/SQL
Control Structures: These are statements that control the flow of execution in your PL/SQL code. They allow you to make decisions, repeat actions, and handle different scenarios.
Why they are important:
Logic and Flexibility: Control structures enable you to write more complex and dynamic PL/SQL code.
Code Reusability: They help you create reusable code blocks that can be called from different parts of your application.
Common Control Structures:
IF-THEN-ELSE: Executes different code blocks based on a condition.
LOOP: Repeats a block of code until a condition is met.
FOR LOOP: Iterates over a range of values.
CASE: Selects a code block to execute based on a value.


5. DML vs. DDL in SQL
DML (Data Manipulation Language): DML statements are used to modify data within tables.
DDL (Data Definition Language): DDL statements are used to define and modify the structure of your database (tables, indexes, etc.).
Examples:
DML:
INSERT INTO customers (name, email) VALUES ('John Doe', 'john.doe@example.com'); (Inserts a new customer)
UPDATE customers SET email = 'john.doe@newdomain.com' WHERE name = 'John Doe'; (Updates a customer’s email)
DELETE FROM customers WHERE customer_id = 123; (Deletes a customer)
DDL:
CREATE TABLE customers (customer_id INT PRIMARY KEY, name VARCHAR(255), email VARCHAR(255)); (Creates a new table)
ALTER TABLE customers ADD COLUMN phone VARCHAR(20); (Adds a new column to a table)
DROP TABLE customers; (Deletes a table)


# MySQL Cheat Sheet

This cheat sheet provides essential MySQL commands for quick reference. It covers database and table management, basic SQL commands, joins, and more.

## Table of Contents
- [Database Commands](#database-commands)
- [Table Commands](#table-commands)
- [Basic SQL Commands](#basic-sql-commands)
- [Conditions & Filtering](#conditions--filtering)
- [Joins](#joins)
- [Aggregate Functions](#aggregate-functions)
- [Group By & Having](#group-by--having)
- [Ordering](#ordering)
- [Limits](#limits)
- [Indexes](#indexes)
- [Transactions](#transactions)
- [User & Privileges](#user--privileges)
- [Export & Import](#export--import)

---

## Database Commands
```sql
-- Create a new database
CREATE DATABASE dbname;

-- Use a database
USE dbname;

-- Show all databases
SHOW DATABASES;

-- Drop a database
DROP DATABASE dbname;
```

## Table Commands
```sql
-- Create a table
CREATE TABLE table_name (
    id INT PRIMARY KEY AUTO_INCREMENT,
    column1 VARCHAR(255),
    column2 INT
);

-- Show all tables
SHOW TABLES;

-- Describe table structure
DESCRIBE table_name;

-- Drop a table
DROP TABLE table_name;

-- Alter table (e.g., adding a new column)
ALTER TABLE table_name ADD column_name VARCHAR(255);

-- Rename table
RENAME TABLE old_name TO new_name;
```

## Basic SQL Commands
```sql
-- Insert data into a table
INSERT INTO table_name (column1, column2) VALUES ('value1', 100);

-- Select all data from a table
SELECT * FROM table_name;

-- Select specific columns
SELECT column1, column2 FROM table_name;

-- Update data
UPDATE table_name SET column1 = 'new_value' WHERE id = 1;

-- Delete data
DELETE FROM table_name WHERE id = 1;

-- Count rows
SELECT COUNT(*) FROM table_name;
```

## Conditions & Filtering
```sql
-- Select with conditions
SELECT * FROM table_name WHERE column1 = 'value';

-- Using AND, OR, NOT
SELECT * FROM table_name WHERE column1 = 'value' AND column2 > 100;
SELECT * FROM table_name WHERE column1 = 'value' OR column2 < 100;
SELECT * FROM table_name WHERE NOT column1 = 'value';

-- BETWEEN operator
SELECT * FROM table_name WHERE column2 BETWEEN 100 AND 200;

-- LIKE operator (pattern matching)
SELECT * FROM table_name WHERE column1 LIKE '%value%';

-- IN operator (matching any value in a list)
SELECT * FROM table_name WHERE column1 IN ('value1', 'value2');
```

## Joins
```sql
-- Inner join
SELECT columns FROM table1 INNER JOIN table2 ON table1.column = table2.column;

-- Left join
SELECT columns FROM table1 LEFT JOIN table2 ON table1.column = table2.column;

-- Right join
SELECT columns FROM table1 RIGHT JOIN table2 ON table1.column = table2.column;
```

## Aggregate Functions
```sql
-- Count rows
SELECT COUNT(*) FROM table_name;

-- Sum of a column
SELECT SUM(column_name) FROM table_name;

-- Average value
SELECT AVG(column_name) FROM table_name;

-- Maximum and minimum value
SELECT MAX(column_name), MIN(column_name) FROM table_name;
```

## Group By & Having
```sql
-- Grouping data
SELECT column, COUNT(*) FROM table_name GROUP BY column;

-- Grouping with condition
SELECT column, COUNT(*) FROM table_name GROUP BY column HAVING COUNT(*) > 1;
```

## Ordering
```sql
-- Order data by column
SELECT * FROM table_name ORDER BY column1 ASC;
SELECT * FROM table_name ORDER BY column2 DESC;
```

## Limits
```sql
-- Limit the number of rows returned
SELECT * FROM table_name LIMIT 10;

-- Limit with offset
SELECT * FROM table_name LIMIT 10 OFFSET 20;
```

## Indexes
```sql
-- Create an index
CREATE INDEX index_name ON table_name (column_name);

-- Drop an index
DROP INDEX index_name ON table_name;
```

## Transactions
```sql
-- Begin transaction
START TRANSACTION;

-- Commit transaction
COMMIT;

-- Rollback transaction
ROLLBACK;
```

## User & Privileges
```sql
-- Create a new user
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

-- Grant privileges
GRANT ALL PRIVILEGES ON dbname.* TO 'username'@'localhost';

-- Revoke privileges
REVOKE ALL PRIVILEGES ON dbname.* FROM 'username'@'localhost';

-- Drop user
DROP USER 'username'@'localhost';
```

## Export & Import
```bash
-- Export database to SQL file
mysqldump -u username -p dbname > backup.sql

-- Import database from SQL file
mysql -u username -p dbname < backup.sql
```


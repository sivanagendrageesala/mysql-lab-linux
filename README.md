# 🐬 MySQL Backup & Restore on Linux

> A practical project that teaches how to create, back up, drop, and restore MySQL databases on Linux. Includes hands-on experience with Git, systemctl, and SQL commands.


---



## ✅ Part 1: Connect to MySQL Server

```bash
systemctl status mysql | grep active
	Verifies if MySQL is running. Output should include Active: active (running).

If it's not running, start it:

bash

sudo systemctl start mysql
Connect to MySQL:

bash

mysql -u sivanagendra -p
# Password: *****

✅ Part 2: Create a Database and Tables

sql
CREATE DATABASE testdb;
USE testdb;

CREATE TABLE employees (
  id INT PRIMARY KEY AUTO_INCREMENT,
  firstname VARCHAR(50),
  lastname VARCHAR(50),
  hiredate DATE
);

CREATE TABLE department (
  id INT PRIMARY KEY AUTO_INCREMENT,
  department_name VARCHAR(100)
);

CREATE TABLE employee_department (
  employee_id INT,
  department_id INT,
  FOREIGN KEY (employee_id) REFERENCES employees(id),
  FOREIGN KEY (department_id) REFERENCES department(id)
);
✅ Part 3: Insert Data

sql
INSERT INTO employees (firstname, lastname, hiredate)
VALUES ('Jane', 'Doe', '2022-01-15'),
       ('John', 'Doe', '2022-01-31');

INSERT INTO department (department_name)
VALUES ('hr'), ('engineering'), ('marketing');

INSERT INTO employee_department (employee_id, department_id)
VALUES (1, 2), (2, 2);

✅ Part 4: Query Data with Joins

sql

SELECT * FROM employees;
SELECT * FROM department;
SELECT * FROM employee_department;

-- Human-friendly join:
SELECT e.firstname, e.lastname, d.department_name
FROM employee_department ed
JOIN employees e ON ed.employee_id = e.id
JOIN department d ON ed.department_id = d.id;

✅ Part 5: Backup and Restore
Backup:

bash

exit  # from MySQL
mysqldump -u sivanagendra -p -B testdb > testdb_backup.sql

Verify:

bash

ls | grep testdb
Drop DB and Restore:

sql
mysql -u sivanagendra -p
DROP DATABASE testdb;
exit
mysql -u sivanagendra -p testdb < testdb_backup.sql


# 🚀 Git + MySQL + systemctl Cheat Sheet (by Siva)
_Last Updated: 2025-06-13_

---

## 🔧 Git Essentials

| Action                     | Command                                  |
|---------------------------|-------------------------------------------|
| Clone a repository        | `git clone https://github.com/user/repo.git` |
| Check status              | `git status`                              |
| Stage changes             | `git add filename` or `git add .`         |
| Commit changes            | `git commit -m "message"`                 |
| Push to GitHub            | `git push origin main`                    |
| Set Git identity          | `git config --global user.name "Siva"`    |
|                          | `git config --global user.email "you@example.com"` |
| Update remote after rename| `git remote set-url origin NEW_URL`       |
| Check remote URL          | `git remote -v`                           |

---

## 🐬 MySQL Basics

| Task                         | Command / SQL                                |
|-----------------------------|-----------------------------------------------|
| Login to MySQL              | `mysql -u sivanagendra -p`                    |
| Show databases              | `SHOW DATABASES;`                             |
| Create new database         | `CREATE DATABASE testdb;`                     |
| Use a database              | `USE testdb;`                                 |
| Create a table (example)    | See `employees` example below                 |
| Insert data                 | `INSERT INTO table (...) VALUES (...);`       |
| View data                   | `SELECT * FROM table;`                        |
| Backup database             | `mysqldump -u user -p -B testdb > backup.sql` |
| Restore database            | `mysql -u user -p testdb < backup.sql`        |

### 👇 Create `employees` Table Example

```sql
CREATE TABLE employees (
  id INT PRIMARY KEY AUTO_INCREMENT,
  firstname VARCHAR(50),
  lastname VARCHAR(50),
  hiredate DATE
);
```

---

## 🖥️ Linux systemctl (Service Management)

| Action                     | Command                          |
|---------------------------|-----------------------------------|
| Check service status      | `systemctl status mysql`          |
| Start MySQL               | `sudo systemctl start mysql`      |
| Stop MySQL                | `sudo systemctl stop mysql`       |
| Enable MySQL on boot      | `sudo systemctl enable mysql`     |
| Disable MySQL on boot     | `sudo systemctl disable mysql`    |
| Grep for active status    | `systemctl status mysql \| grep active` |

---

✅ Created by **Siva Nagendra** for Linux + MySQL + Git practice.

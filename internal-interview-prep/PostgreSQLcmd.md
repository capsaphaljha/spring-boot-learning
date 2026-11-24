

when you are running on window you need to run below command after setting up env variable:

```cmd
psql -U postgres
```

here you must use username to login into database


markdown
# PostgreSQL Cheat Sheet & Windows Quick Start

A quick reference guide for installing PostgreSQL on Windows, connecting via `psql`, and translating common MySQL commands to PostgreSQL.

---

## 1. Windows Installation & Connection

1. Download the Windows installer from [PostgreSQL Downloads](https://postgresql.org).
2. Run the `.exe` setup wizard, select **PostgreSQL Server**, **pgAdmin 4**, and **Command Line Tools (`psql`)**.
3. Set a password for the default `postgres` superuser account and keep the default port (`5432`).

### Connecting via `psql`
By default, running `psql.exe` directly attempts to log in with your Windows username. Connect as the `postgres` superuser instead:

```cmd
psql -U postgres
```
*(Note: Keystrokes are hidden when typing your password—nothing will appear on screen. Type your password and press **Enter**.)*

---

## 2. `psql` Navigation Commands (vs. MySQL)

PostgreSQL uses backslash (`\`) meta-commands in `psql` instead of MySQL's text commands:

| Task | PostgreSQL (`psql`) | MySQL Equivalent |
| :--- | :--- | :--- |
| **List all databases** | `\l` or `\list` | `SHOW DATABASES;` |
| **Switch database** | `\c database_name` | `USE database_name;` |
| **List all tables** | `\dt` | `SHOW TABLES;` |
| **Describe table structure** | `\d table_name` | `DESCRIBE table_name;` |
| **List all users/roles** | `\du` | `SELECT user FROM mysql.user;` |
| **List all schemas** | `\dn` | `SHOW SCHEMAS;` |
| **Show command help** | `\?` | `HELP;` |
| **Exit the shell** | `\q` | `EXIT;` or `QUIT;` |

---

## 3. Common SQL Commands

Once connected to a database, standard SQL commands work similarly across both systems (always end statements with a semicolon `;`):

### Database & Table Management
```sql
-- Create a new database
CREATE DATABASE shop;

-- Create a table (uses SERIAL instead of MySQL's AUTO_INCREMENT)
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Drop a table
DROP TABLE users;
```

### CRUD Operations
```sql
-- Insert data
INSERT INTO users (name, email) 
VALUES ('Alex', 'alex@example.com');

-- Read data
SELECT * FROM users;

-- Update data
UPDATE users 
SET name = 'Sam' 
WHERE id = 1;

-- Delete data
DELETE FROM users 
WHERE id = 1;
```

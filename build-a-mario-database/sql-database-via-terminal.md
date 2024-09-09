# SQL Database via Terminal

<aside>
⚠️ Login to mysql in terminal on localhost

`> sudo mysql -u root -p`
`> Password: (Sudo password)`
`> Enter password (MySQL password)`

</aside>

### Shortcuts

`\l` List databases

`\c` Connect to a database

`\d` Display database tables

`\d table_name` Display specific table

## Commands

### Managing databases

```sql
CREATE DATABASE data_basename;

DROP DATABASE database_name;

ALTER DATABASE database_name RENAME TO new_database_name;
```

### Managing tables

```sql
CREATE TABLE table_name();

// Creating table with columns in one command
CREATE TABLE table_name(column_name DATATYPE CONSTRAINTS);

DROP TABLE table_name;
```

### Managing columns

```sql

ALTER TABLE table_name ADD COLUMN column_name DATATYPE;

ALTER TABLE table_name DROP COLUMN column_name;

// Renaming
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;

// Adding primary key
ALTER TABLE table_name ADD PRIMARY KEY(column_name);

// Deleting primary key
ALTER TABLE table_name DROP CONSTRAINT [table_name]_pkey;

// Setting a column as unique
ALTER TABLE table_name ADD UNIQUE(column_name);

// Setting a column as not null
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```

### Managing table rows

```sql

// Adding a single row
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);

// Adding multiple rows at once
INSERT INTO characters(name, homeland, favorite_color)
VALUES('Mario', 'Mushroom Kingdom', 'Red'),
('Luigi', 'Mushroom Kingdom', 'Green'),
('Peach', 'Mushroom Kingdom', 'Pink');

// Deleting a row
DELETE FROM table_name WHERE condition;

// Updating value
UPDATE table_name SET column_name=new_value WHERE condition;
UPDATE characters SET name='Mario' WHERE character_id=4;

// Updating multiple values at once
UPDATE characters SET name='Mario', color='Red' WHERE character_id=4;

// Updating multiple rows with multiple conditions
UPDATE characters SET game='Mario Games' WHERE game='Super Mario Bros.' OR game='Super Mario Bros. 2';

// Updating all rows by removing the WHERE condition
UPDATE characters SET name='Its me a Mario!';

```

```sql
// Creating a foreign key
ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name);
```

### Queries

When you search something on Google you are performing a query but database queries are requests made to the database for a specific information that you write using SQL.

```sql
SELECT * FROM table_name;

// Ordering
SELECT columns FROM table_name ORDER BY column_name;

// Performing a full join table with one-to-one or one-to-many relationships.
SELECT columns FROM table_1 FULL JOIN table_2 ON table_1.primary_key_column = table_2.foreign_key_column;

// Performing a many-to-many join table
SELECT columns FROM junction_table
FULL JOIN table_1 ON junction_table.foreign_key_column = table_1.primary_key_column
FULL JOIN table_2 ON junction_table.foreign_key_column = table_2.primary_key_column;

-- Ways to compare or compose
-- <, >, <=, >=, =, <> (not equal), AND, OR, IN

SELECT * FROM users WHERE name IN ('David', 'Jack');
```

### Data Types

`INT` Integer

`VARCAR(MAX_LEN)` Short characters string. It requires a max length.

`SERIAL` creates a `INT` column with a `NOT NULL` constraint and increment the number when a new row is added.

`DATE` type for dates

`NUMERIC(precision, scale)` Used for decimal numbers
precision = Total of numbers

scale = Total of digits after the `.`

```sql
+--------------+----------+
|  Data Type   |  Number  |
+--------------+----------+
| NUMERIC(4,2) |  12.34   |
| NUMERIC(1,1) |   1.2    |
```

Relationship

### Constraints

`NOT NULL`

Is the SQL way to say the field is required

```sql
CREATE TABLE student (
    name VARCHAR(20) NOT NULL
);

INSERT INTO student(name) VALUES(NULL);

> Column 'name' cannot be null
```

`UNIQUE`

Avoid duplicate values on the same table

```sql
CREATE TABLE student (
    ssn INT UNIQUE
);

// Try to insert twice
INSERT INTO student(ssn) VALUES(123);

> Duplicate entry '123' for key 'student.ssn'
```

`DEFAULT`

Set a default value to the field if not passed any

```sql
CREATE TABLE student (
    student_id INT,
    major VARCHAR(25) DEFAULT 'Still deciding'
);

// Insert a student without major
INSERT INTO student(student_id) VALUES(1);

SELECT * FROM student;

// Output
+--------------+-------------------+
|  student_id  |       major       |
+--------------+-------------------+
|      1       |  'Still deciding' |
```

`AUTO_INCREMENT`

Every time you insert a new row the database will create an incremented value for that field. So you could use to generate an id on each data insert you do.

```sql
CREATE TABLE student (
    student_id INT AUTO_INCREMENT,
		name VARCHAR(20) NOT NULL,
		PRIMARY KEY(student_id)
);

INSERT INTO student(name) VALUES('John'),('Marcus'),('David');

SELECT * FROM student;

// Output
+--------------+-------------------+
|  student_id  |       name        |
+--------------+-------------------+
|      1       |      'John'       |
+--------------+-------------------+
|      2       |      'Marcus'     |
+--------------+-------------------+
|      3       |      'David'      |
+--------------+-------------------+
```

### Dictionary

**Primary Key** is a column that can serve as unique identifier to each row. Can only be one primary key per table.

**Foreign Key** is a column created to reference another table's row

**Junction Table** is a table that references two other tables creating a many-to-many relationship between tables.

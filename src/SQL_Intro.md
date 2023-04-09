# SQL Intro
## What is SQL?
SQL, or Structured Query Language, is a language designed to allow both technical and non-technical users query, manipulate, and transform data from a relational database. And due to its simplicity, SQL databases provide safe and scalable storage for millions of websites and mobile applications.
## SELECT queries
 a SELECT query is a type of query that is used to retrieve data from a database. It is one of the most commonly used SQL commands and allows you to specify what data you want to retrieve and from which table or tables.
- Select query for all columns
``` SQL
SELECT * 
FROM mytable;
```
- Select query for a specific columns
``` SQL
SELECT column, another_column, …
FROM mytable;
```
<br>
<br>

## Queries with constraints
- `WHERE`: used to filter the rows that are returned in a query result
- `AND` or `OR`: the `AND` and `OR` operators are used to combine multiple conditions in the `WHERE` clause of a query.
``` SQL
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
```
<br>
<br>

some useful operators that you can use for numerical data (ie. integer or floating point):<br>

| Operator             | Condition                                      | SQL Example                    |
|----------------------|------------------------------------------------|--------------------------------|
| =, !=, < <=, >, >=   | Standard numerical operators                   | `col_name != 4`                |
| BETWEEN … AND …      | Number is within range of two values (inclusive)| `col_name BETWEEN 1.5 AND 10.5` |
| NOT BETWEEN … AND …  | Number is not within range of two values (inclusive)| `col_name NOT BETWEEN 1 AND 10` |
| IN (…)               | Number exists in a list                        | `col_name IN (2, 4, 6)`         |
| NOT IN (…)           | Number does not exist in a list                | `col_name NOT IN (1, 3, 5)`     |

<br>

common text-data specific operators:

| Operator | Condition                                            | Example                                 |
|----------|------------------------------------------------------|-----------------------------------------|
| =        | Case sensitive exact string comparison               | `col_name = "abc"`                      |
| != or <> | Case sensitive exact string inequality comparison     | `col_name != "abcd"` or `col_name <> "abcd"` |
| LIKE     | Case insensitive exact string comparison             | `col_name LIKE "ABC"`                   |
| NOT LIKE | Case insensitive exact string inequality comparison   | `col_name NOT LIKE "ABCD"`              |
| %        | Used anywhere in a string to match zero or more characters (only with LIKE or NOT LIKE) | `col_name LIKE "%AT%"` (matches "AT", "ATTIC", "CAT" or even "BATS") |
| _        | Used anywhere in a string to match a single character (only with LIKE or NOT LIKE) | `col_name LIKE "AN_"` (matches "AND", but not "AN") |
| IN (…)   | String exists in a list                              | `col_name IN ("A", "B", "C")`           |
| NOT IN (…) | String does not exist in a list                      | `col_name NOT IN ("D", "E", "F")`       |

## Filtering and sorting Query results
- `DISTINCT`: used to retrieve only unique/distinct values from a column in a table.
```SQL
SELECT DISTINCT department FROM employees;
```
- `ORDER BY`: is used to sort the results of a query based on one or more columns. You can specify the order of sorting for each column by using the `ASC` (ascending) or `DESC`.
```SQL
SELECT * FROM employees ORDER BY last_name ASC, first_name ASC;
``` 
- `LIMIT`:  is used to limit the number of rows returned by a query. You specify the number of rows to return after the `LIMIT` keyword.
```SQL
SELECT * FROM employees LIMIT 10;
```
## Multi-table queries with JOINs
In SQL (Structured Query Language), an inner join is a type of join operation that combines rows from two or more tables based on a matching condition specified in the ON clause. The result of an inner join is a new table that contains only the rows from both tables that satisfy the join condition.

```SQL
SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
# Inserting rows
`INSERT`: used to add one or more new records, also known as rows, to a table. The `INSERT` statement can be used to add data to a specific column or to all columns in the table.
```SQL
INSERT INTO mytable
VALUES (value_or_expr, another_value_or_expr, …),
       (value_or_expr_2, another_value_or_expr_2, …),
       …;
```
# Updating rows
`UPDATE`: used to modify existing records, also known as rows, in a table. The `UPDATE` statement can change the values of one or more columns for one or more records in a table.
```SQL
UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition;
```
# Deleting rows
`DELETE`: used to remove one or more records, also known as rows, from a table. The `DELETE` statement can be used to remove specific records that meet certain conditions or to remove all records from a table.
```SQL
DELETE FROM mytable
WHERE condition;
```
# Creating tables
`CREATE TABLE`: used to create a new table in a database. The `CREATE TABLE` statement defines the structure of the table, including the column names, data types, and any constraints on the data.
```SQL
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);
```
<br>

## Table data types

| Data type                | Description                                                                                                                                      |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `INTEGER`, `BOOLEAN`     | The integer datatypes can store whole integer values like the count of a number or an age. In some implementations, the boolean value is just represented as an integer value of just 0 or 1. |
| `FLOAT`, `DOUBLE`, `REAL` | The floating point datatypes can store more precise numerical data like measurements or fractional values. Different types can be used depending on the floating point precision required for that value. |
| `CHARACTER(num_chars)`, `VARCHAR(num_chars)`, `TEXT` | The text based datatypes can store strings and text in all sorts of locales. The distinction between the various types generally amount to underlaying efficiency of the database when working with these columns. Both the `CHARACTER` and `VARCHAR` (variable character) types are specified with the max number of characters that they can store (longer values may be truncated), so can be more efficient to store and query with big tables. |
| `DATE`, `DATETIME` | SQL can also store date and time stamps to keep track of time series and event data. They can be tricky to work with especially when manipulating data across timezones. |
| `BLOB` | Finally, SQL can store binary data in blobs right in the database. These values are often opaque to the database, so you usually have to store them with the right metadata to requery them. |
<br>

## Table constraints

| Constraint         | Description                                                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `PRIMARY KEY`      | This means that the values in this column are unique, and each value can be used to identify a single row in this table.                                       |
| `AUTOINCREMENT`    | For integer values, this means that the value is automatically filled in and incremented with each row insertion. Not supported in all databases.             |
| `UNIQUE`           | This means that the values in this column have to be unique, so you can't insert another row with the same value in this column as another row in the table. Differs from the `PRIMARY KEY` in that it doesn't have to be a key for a row in the table. |
| `NOT NULL`         | This means that the inserted value cannot be `NULL`.                                                                                                          |
| `CHECK (expression)` | This allows you to run a more complex expression to test whether the values inserted are valid. For example, you can check that values are positive, or greater than a specific size, or start with a certain prefix, etc. |
| `FOREIGN KEY`      | This is a consistency check which ensures that each value in this column corresponds to another value in a column in another table. For example, if there are two tables, one listing all Employees by ID, and another listing their payroll information, the `FOREIGN KEY` can ensure that every row in the payroll table corresponds to a valid employee in the master Employee list. | 
## Relational database management system

- data stored in multiple tables

## Different types of languages in SQL
1. Data definition language(DDL)
2. Data manipulation language(DML)
3. Data query language(DQL)
4. Data control Language(DCL)
5. Data transaction language(DTL)


## commands in MySQL

1. create a schema
=> CREATE SCHEMA schema_name

2. use a schema
=> USE schema_name

3. create Table
=> CREATE TABLE table_name (
	column1 datatype,
	column2 datatype,
	column3 datatype,
	PRIMARY KEY (column name)
)

4. Adding or Removing column in table
	- Adding column => 
			ALTER table_name
			ADD column_name datatype `[AFTER column_name(position)]`
	- Removing Column =>
			ALTER table_name
			DROP column_name

5. Dropping Schema and Table
	- Dropping Schema =>
			DROP schema_name
	- Dropping table =>
			DROP table_name

6. Insert new row in table
	- INSERT INTO table_name VALUES
			(field1, field2, ...);

7. Update value of a cell
	- UPDATE table_name
			SET column_name = value
			WHERE column_name IN (value, value)
## Primary Key and Foreign Key
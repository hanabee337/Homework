# SQL Tutorial
Reference : <http://www.w3schools.com/sql/default.asp>

## SQL
>	a standard language for accessing and manipulationg databases.
## What Can SQL do ?
- SQL can execute queries against a database
- SQL can retrieve data from a database
- SQL can insert records in a database
- SQL can update records in a database
- SQL can delete records from a database
- SQL can create new databases
- SQL can create new tables in a database
- SQL can create stored procedures in a database
- SQL can create views in a database

### Table
> a collection of related data entries and it consists of columns and rows.

# SQL Syntax
### Database Tables
- A database most often contains one or more tables. Each table is identified by a name.
- Tables contain records (rows) with data.

### SQL Statements
- Most of the actions you need to perform on a database are done with SQL statements.
- The following SQL statement selects all the records in the "Customers" table:  
```
SQL
Example
SELECT * FROM Customers;
```  

- SQL keywords are NOT case sensitive: select is the same as SELECT.
- Semicolon is the standard way to separate each SQL statement in database systems  
that allow more than one SQL statement to be executed in the same call to the server.

### Some of The Most Important SQL Commands
- SELECT - extracts data from a database
- UPDATE - updates data in a database
- DELETE - deletes data from a database
- INSERT INTO - inserts new data into a database
- CREATE DATABASE - creates a new database
- ALTER DATABASE - modifies a database
- CREATE TABLE - creates a new table
- ALTER TABLE - modifies a table
- DROP TABLE - deletes a table
- CREATE INDEX - creates an index (search key)
- DROP INDEX - deletes an index

### SQL Quick Reference From W3Schools
- AND Operator
	- displays a record if both the first condition AND the second condition are true.
	- The following SQL statement selects all customers from the country "Germany" AND the city "Berlin", in the "Customers" table:  
	```
	SELECT * FROM Customers
	WHERE Country='Germany'
	AND City='Berlin';
	```

- OR Operator
	- displays a record if either the first condition OR the second condition is true.

	- The following SQL statement selects all customers from the city "Berlin" OR "München", in the "Customers" table:  
	```
	SELECT * FROM Customers
	WHERE City='Berlin'
	OR City='München';
	```

- ALTER TABLE Statement
	- used to add, delete, or modify columns in an existing table
	- SQL ALTER TABLE Syntax
	- To add a column in a table, use the following syntax:  
	```
	ALTER TABLE table_name
	ADD column_name datatype
	```
	
	- To delete a column in a table, use the following syntax (notice that some database systems don't allow deleting a column):  
	```
	ALTER TABLE table_name
	DROP COLUMN column_name
	```
- AS (alias)
	- used to temporarily rename a table or a column heading.
	- used to give a database table, or a column in a table, a temporary name.
	- Basically aliases are created to make column names more readable.
	- Aliases can be useful when:
		- There are more than one table involved in a query
		- Functions are used in the query
		- Column names are big or not very readable
		- Two or more columns are combined together
	
	- SQL Alias Syntax for Columns  
	```
	SELECT column_name AS alias_name
	FROM table_name;
	```

	- SQL Alias Syntax for Tables  
	```
	SELECT column_name(s)
	FROM table_name AS alias_name;
	```

	- Alias Example for Tables
		- The following SQL statement selects all the orders from the customer with CustomerID=4 (Around the Horn). We use the "Customers" and "Orders" tables, and give them the table aliases of "c" and "o" respectively (Here we have used aliases to make the SQL shorter):
	```
	SELECT o.OrderID, o.OrderDate, c.CustomerName
	FROM Customers AS c, Orders AS o
	WHERE c.CustomerName="Around the Horn" AND c.CustomerID=o.CustomerID;
	```

- BETWEEN Operator
	- used to select values within a range.
	- The values can be numbers, text, or dates.
	- SQL BETWEEN Syntax  
	```
	SELECT column_name(s)
	FROM table_name
	WHERE column_name BETWEEN value1 AND value2;
	```
	- The following SQL statement selects all products with a price BETWEEN 10 and 20:  
	```
	SELECT * FROM Products
	WHERE Price BETWEEN 10 AND 20;
	```
	-	For more examples, plz refer to <http://www.w3schools.com/sql/sql_between.asp>

- CREATE DATABASE Statement
	- used to create a database.
	```
	CREATE DATABASE dbname;
	```
- CREATE TABLE Statement
	- used to create a table in a database.
	- Tables are organized into rows and columns; and each table must have a name.
	- CREATE TABLE Syntax
	```
	CREATE TABLE table_name
	(
	column_name1 data_type(size),
	column_name2 data_type(size),
	column_name3 data_type(size),
	....
	);
	```
	-	SQL CREATE TABLE Example
		- Now we want to create a table called "Persons" that contains five columns: PersonID, LastName, FirstName, Address, and City.
	```
	CREATE TABLE Persons
	(
	PersonID int,
	LastName varchar(255),
	FirstName varchar(255),
	Address varchar(255),
	City varchar(255)
	);
	```

- Views
	1. CREATE VIEW Statement
		- a view is a virtual table based on the result-set of an SQL statement.
		- A view contains rows and columns
		- You can add SQL functions, WHERE, and JOIN statements to a view and present the data as if the data were coming from one single table.
		- SQL CREATE VIEW Syntax  
		``` 
		CREATE VIEW view_name AS
		SELECT column_name(s)
		FROM table_name
		WHERE condition
		```
	2. Updating a View  
		```
		CREATE OR REPLACE VIEW view_name AS  
		SELECT column_name(s)  
		FROM table_name  
		WHERE condition  
		```  
	3. Dropping a View   
		```
		DROP VIEW view_name
		```
- DELETE
	- used to delete records in a table.
	- SQL DELETE Syntax  
	```
	DELETE FROM table_name  
	WHERE some_column=some_value;
	```
	- Be very careful when deleting records. You cannot undo this statement!

- DROP 
	- Indexes, tables, and databases can easily be deleted/removed with the DROP statement.
	- The DROP INDEX statement is used to delete an index in a table.  
	```
	DROP INDEX index_name ON table_name
	```
	- The DROP TABLE statement is used to delete a table.  
	```
	DROP TABLE table_name
	```
	- The DROP DATABASE statement is used to delete a database.  
	```
	DROP DATABASE database_name
	```
- The TRUNCATE TABLE Statement
	- What if we only want to delete the data inside the table, and not the table itself?
	- Then, use the TRUNCATE TABLE statement:  
	```
	TRUNCATE TABLE table_name
	```

- SELECT
	- used to select data from a database.
	- The result is stored in a result table, called the result-set.
	- Syntax  
	```
	SELECT column_name,column_name
	FROM table_name;
	```  
	and  
	```
	SELECT * FROM table_name;
	```  

- SELECT DISTINCT Statement
	- used to return only distinct (different) values.
	- In a table, a column may contain many duplicate values; and sometimes you only want to list the different (distinct) values.
	- The DISTINCT keyword can be used to return only distinct (different) values.
	- Syntax  
	```
	SELECT DISTINCT column_name,column_name
	FROM table_name;
	```  
	- Example
		- the following SQL statement selects only the distinct values from the "City" columns from the "Customers" table:
	```
	SELECT DISTINCT City FROM Customers;
	```  

- SELECT INTO Statement
	- selects data from one table and inserts it into a new table.
	- Syntax  
	```
	SELECT *
	INTO newtable [IN externaldb]
	FROM table1;
	```
	- Examples
		- Create a backup copy of Customers:  
		```
		SELECT *
		INTO CustomersBackup2013
		FROM Customers;
		```
- SELECT TOP
	- used to specify the number of records to return.
	- Syntax  
	```
	SELECT TOP number|percent column_name(s)
	FROM table_name;
	```
	- Examples
		- The following SQL statement selects the two first records from the "Customers" table:  
		```
		SELECT TOP 2 * FROM Customers;
		```  

		- The following SQL statement selects the first 50% of the records from the "Customers" table:  
		```
		SELECT TOP 50 PERCENT * FROM Customers;
		```  


- UPDATE
	- used to update existing records in a table.
	- Syntax  
	```
	UPDATE table_name
	SET column1=value1,column2=value2,...
	WHERE some_column=some_value;
	```
	- To update more than one column, use a comma as seperator.
	- The WHERE clause specifies which record or records that should be updated. **If you omit the WHERE clause, all records will be updated!**

- GROUP BY Statement
	- used in conjunction with the aggregate functions to group the result-set by one or more columns.
	- Syntax
	```
	SELECT column_name, aggregate_function(column_name)
	FROM table_name
	WHERE column_name operator value
	GROUP BY column_name;
	```
	- Example
		- The following SQL statement counts as orders grouped by shippers:  
	```
	SELECT Shippers.ShipperName,COUNT(Orders.OrderID) 
	AS NumberOfOrders FROM Orders
	LEFT JOIN Shippers
	ON Orders.ShipperID=Shippers.ShipperID
	GROUP BY ShipperName;
	```
- ORDER BY Keyword
	- used to sort the result-set by one or more columns.
	- sorts the records in ascending order by default.
	- Syntax  
	```
	SELECT column_name, column_name
	FROM table_name
	ORDER BY column_name ASC|DESC, column_name ASC|DESC;
	```
	- Example
		- The following SQL statement selects all customers from the "Customers" table, sorted by the "Country" column:
	```
	SELECT * FROM Customers
	ORDER BY Country;
	```  

- LIKE Operator
	- used in a WHERE clause to search for a specified pattern in a column.
	- Syntax  
	```
	SELECT column_name(s)
	FROM table_name
	WHERE column_name LIKE pattern;
	```
	- Example
		- The following SQL statement selects all customers with a City starting with the letter "s":	
		```
		SELECT * FROM Customers
		WHERE City LIKE 's%';
		```

- IN Operator
	- allows you to specify multiple values in a WHERE clause.
	- Syntax
	```
	SELECT column_name(s)
	FROM table_name
	WHERE column_name IN (value1,value2,...);
	```
	- Example 
		- The following SQL statement selects all customers with a City of "Paris" or "London":
	```
	SELECT * FROM Customers
	WHERE City IN ('Paris','London');
	```

- INSERT INTO Statement
	- used to insert new records in a table.
	- Syntax
		1. first form does not specify the column names where the data will be inserted, only their values.  
			```
			INSERT INTO table_name
			VALUES (value1,value2,value3,...);
			```
			- Example
			```
			INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
			VALUES ('Cardinal','Tom B. Erichsen','Skagen 21','Stavanger','4006','Norway');
			```
		2. second form specifies both the column names and the values to be inserted.  
			```
			INSERT INTO table_name (column1,column2,column3,...)
			VALUES (value1,value2,value3,...);
			```
			- Example  
			```
			INSERT INTO Customers (CustomerName, City, Country)
			VALUES ('Cardinal', 'Stavanger', 'Norway');
			```

- HAVING Clause
	- added to SQL because the WHERE keyword could not be used with aggregate functions.
	- Syntax
	```
	SELECT column_name, aggregate_function(column_name)  
	FROM table_name  
	WHERE column_name operator value
	GROUP BY column_name  
	HAVING aggregate_function(column_name) operator value;
	```
	- Example
		- Now we want to find  if any of the employees has registered more than 10 orders.
		```
		SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders FROM (Orders
		INNER JOIN Employees
		ON Orders.EmployeeID=Employees.EmployeeID)
		GROUP BY LastName
		HAVING COUNT(Orders.OrderID) > 10;
		```

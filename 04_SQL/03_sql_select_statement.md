https://www.javatpoint.com/sql-select


# SQL SELECT Statement

The SELECT statement is the most commonly used command in Structured Query Language. It is used to access the records from one or more database tables and views. It also retrieves the selected data that follow the conditions we want.

By using this command, we can access the particular record from the particular column of the table. The table which stores the record returned by the SELECT statement is called a result-set table.

### Sytax of SELECT Statement in SQL

```sql
SELECT Column_Name_1, Column_Name_2, ....., Column_Name_N FROM Table_Name;
```

In this SELECT syntax, **Column_Name_1, Column_Name_2, ....., Column_Name_N** are the name of those columns in the table whose data we want to read. If you want access all rows from all fields of the table, use the following sytax with * asterisk sign:

```sql
SELECT * FROM table_name;
```

### SELECT Statement with WHERE clause

The WHERE clause is used with SELECT statement to return only those rows from table, which satisfy the specified condition in the query.

In SQL, the WHERE clause is not only used with SELECT, but it is also used with other SQL statements such as UPDATE, ALTER, and DELETE statements.

```sql
SELECT * FROM Name_of_Table WHERE [condition];

SELECT * FROM Employee_Details WHERE Emp_Panelty = 500;
```

In the syntax, we specify the condition in the WHERE clause using SQL logical or comparison operators.

### SQL SELECT Statement with GROUP BY clause

The GROUP BY clause is used with the SELECT statement to show the common data of the column from the table:

```sql
SELECT column_Name_1, column_Name_2, ....., column_Name_N, aggregate_function_name(column_Name2) FROM table_name GROUP BY column_Name1;

SELECT COUNT (Car_Name), Car_Price FROM Cars_Details GROUP BY Car_Price;  
```

### SQL SELECT Statement with HAVING clause

The HAVING clause in the SELECT statement creates a selection in those groups which are defined by the GROUP BY clause.

```sql
SELECT column_Name_1, column_Name_2, ....., column_Name_N aggregate_function_name(column_Name_2) FROM table_name GROUP BY column_Name1 HAVING;

SELECT SUM(Employee_Salary), Employee_City FROM Employee_Having GROUP BY Employee_City HAVING SUM(Employee_Salary)>5000;
```

### SELECT Statement with ORDER BY clause

The ORDER BY clause with the SQL SELECT statement shows the records or rows in a sorted manner. The ORDER BY clause arranges the values in both ascending and descending order. Few database systems arrange the values of column in ascending order by default.

```sql
SELECT Column_Name_1, Column_Name_2, ....., column_Name_N FROM table_name WHERE [Condition] ORDER BY[column_Name_1, column_Name_2, ....., column_Name_N asc | desc ];

SELECT * FROM Employee_Order ORDER BY Emp_Salary DESC;
```


## SQL SELECT UNIQUE

Actually, there is no difference between DISTINCT and UNIQUE.

**SELECT UNIQUE** is an old syntax which was used in oracle description but later ANSI standard defines DISTINCT as the officail keyword. After that oracle also added DISTINCT but did not withdraw the service of UNIQUE keyword for the sake of backward compatibility.

```sql
SELECT UNIQUE column_name  
FROM table_name;
```

## SQL SELECT DISTINCT

The **SQL DISTINCT command** is used with SELECT keyword to retrieve only distinct or unique data.

```sql
SELECT DISTINCT column_name ,column_name  
FROM  table_name;
```

## SQL SELECT COUNT

The **SQL COUNT()** is a function that returns the number of records of the table in the output. This function is used with the SQL SELECT statement.

```sql
SELECT COUNT(column_name) FROM table_name;  
```

In the syntax, we have to specify the column's name after the COUNT keyword and the name of the table on which the COUNT function is to be executed.

**NULL** values are excluded from the count function.

### SELECT COUNT(*) function in SQL

The COUNT(*) fucntions in SQL shows all the NULL and Non-NULL records present in the table.

```sql
SELECT COUNT(*) FROM table_name;
```

### SQL COUNT() function with WHERE clause

We can also use the COUNT() function with the WHERE clause. The COUNT function with WHERE clause in the SELECT statement shows those records that matched the specifed criteria.

```sql
SELECT COUNT(column_name) FROM table_name WHERE [condition];
```

### SQL COUNT function with DISTINCT keyword

The DISTINCT keyword with COUNT function shows only the numbers of unique rows of a column.

```sql
SELECT COUNT(DISTINCT column_name) FROM table_name WHERE [condition];
```

## SQL SELECT TOP / LIMIT / FETCH FIRST / ROWNUM

The **SELECT TOP** statement in SQL shows the limited number of records or rows from the database table. The TOP clause in the statement specifies how many rows are returned. It shows the top N number of rows from the tables in the output. This clause is used when there are thousands of records stored in the database tables.

All the database systems do not support the TOP keyword for selecting the limited number of records. Oracle supports the ROWNUM keyword, and MySQL supports the LIMIT keyword.

```sql
SELECT TOP number | percent column_Name1, column_Name2, ....., column_NameN  FROM table_name WHERE [Condition];
```

### Syntax of LIMIT clause in MySQL

```sql
SELECT column_Name1,column_Name2, ....., column_NameN FROM table_name LIMIT value;
```

### Syntax of ROWNUM keyword in WHERE clause in Oracle database

```sql
SELECT column_Name1,column_Name2, ....., column_NameN FROM table_name WHERE ROWNUM <= value;
```

## SQL SELECT RANDOM

The SQL SELECT RANDOM() function returns the random row. There are a lot of ways to select a random record or row from a DB table. Each DB server needs different SQL syntax.

If you want to select a random row with **MySQL**:
```sql
SELECT column FROM table
ORDER BY RAND()
LIMIT 1;
```

**MS SQL Server**:
```sql
SELECT TOP 1 column FROM table
ORDER BY NEW ID();
```

**Oracle DB**:
```sql
SELECT column FROM
(SELECT column FROM table
ORDER BY dbms_random.value)
WHERE rownum =1;
```

**PostgreSQL**:
```sql
SELECT column FROM table
ORDER BY RAND()
LIMIT 1;
```

## SQL SELECT IN

SQL IN is an operator used in a SQL query to help reduce the need to use multiple SQL "OR" conditions. It is used in SELECT, INSERT, UPDATE or DELETE statement.

```sql
SELECT * FROM students
WHERE students_name IN ( Amit , Raghav, Rajeev);

SELECT * FROM marks
WHERE roll_no IN (001, 023, 024);
```

## SQL SELECT from Multiple Tables

This statement is used to retrieve fields from multiple tables. To do so, we need to use join query to get data from multiple tables.

```sql
SELECT orders.order_id, suppliers.name
FROM suppliers
INNER JOIN orders
ON suppliers.supplier_id = orders.supplier_id
ORDER BY order_id;

SELECT p. p_id, p.cus_id, p.p_name, c1.name1, c2.name2
FROM product AS p
LEFT JOIN customer1 AS c1 ON p.cus_id=c1.cus_id
LEFT JOIN customer2 AS c2 ON p.cus_id = c2.cus_id;
```

## SQL SELECT DATE

SQL SELECT DATE is used to retrieve a date from a DB.

```sql
SELECT * FROM 
table-name WHERE your date-column >= '2013-12-12';
```

Let's see the another query to get all the records after '2013-12-12' and before '2013-12-13' date.

```sql
SELECT* FROM
table-name where your date-column < '2013-12-13' and your date-column >= '2013-12-12';
```

If you want to compare the dates within the query, you should use BETWEEN operator to do this.

```sql
SELECT * FROM
table_name WHERE yourdate BETWEEN '2012-12-12' and '2013-12-12';
```

Or if you are looking for one date in particular you can use. You should change the date parameter into the acceptable form.

```sql
SELECT* FROM
table_name WHERE cast(datediff (day, 0, yourdate) as datetime) = '2012-12-12';
```

## SQL SELECT SUM

It is used in a SQL query to return summed value of an expression.

```sql
SELECT SUM (expression) FROM tables
WHERE conditions;
```

Expression may be numeric field or formula.

### SQL SUM example with single field

```sql
SELECT SUM (salary) AS "Total Salary"
FROM employees
WHERE salary > 20000;
```

### SQL SUM example with SQL DISTINCT

```sql
SELECT SUM (DISTINCT salary) AS "Total Salary"
FROM employees
WHERE salary > 20000;
```

### SQL SUM example with SQL GROUP BY

```sql
SELECT department, SUM (sales) AS "Total Sales"
FROM order_details
GROUP BY department;
```

## SQL SELECT NULL

First of all we should know that what null value is? **Null** values are used to represent missing unknown data.

There can be two conditions:
1. Where SQL is NULL.
2. Where SQL is NOT NULL.

If in a table, a column is optional, it is very easy to insert data in column or update an existing record without adding a value in this column. This means that field has null value.

### Where SQL is NULL

How to select records with null values only? Let see the query example to get all the records where value is NULL.

```sql
SELECT SIR_NAME, NAME, MARKS FROM STUDENTS
WHERE MARKS IS NULL;
```

### Where SQL is NOT NULL

```sql
SELECT SIR_NAME, FIRSTNAME, MARKS FROM STUDENTS
WHERE MARKS IS NOT NULL;
```
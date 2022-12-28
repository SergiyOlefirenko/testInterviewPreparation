https://www.javatpoint.com/sql-insert-multiple-rows


# SQL INSERT STATEMENT

SQL INSERT statement is a SQL query. It is used to insert a single or a multiple records in a table.

There are two ways to insert data in a table:
1. By SQL insert into statement
    1) By specifying column names
    2) Without specifying column names
2. By SQL insert into select statement

### 1) Inserting data directly into a table

You can insert a row in the table by using SQL INSERT INTO command. There are two ways to insert values in a table.

- **In the first method there is no need to specify the column name where the data will be inserted, you need only their values.**
```sql
INSERT INTO table_name
VALUES (value1, value2, value3....);
```

- **The second method specifies both the column name and values which  you want to insert.**
```sql
INSERT INTO table_name (column1, column2, column3....)
VALUES (value1, value2, value3.....);
```

### 2) Inserting data through SELECT statement

**SQL INSERT INTO SELECT** syntax
```sql
INSERT INTO table_name
[(column1, column2, .... column)]
SELECT column1, column2, .... Column N
FROM table_name [WHERE condition];
```

## SQL INSERT Multiple Rows

Many times developers ask that is it possible to insert multiple rows into a single table in a single statement.

```sql
INSERT INTO student(ID, Name, Percentage, Location, DateOfBirth)
VALUES
    (1, "Manthan Koli", 79, "Delhi", "2003-08-20"),
    (2, "Dev Dixit", 75, "Pune", "1999-06-17"),
    (3, "Aakash Deshmukh", 87, "Mumbai", "1997-09-12"),
    (4, "Aaryan Jaiswal", 90, "Chennai", "2005-10-02"),
    (5, "Rahul Khanna", 92, "Ambala", "1996-03-04"),
    (6, "Pankaj Deshmukh", 67, "Kanpur", "2000-02-02"),
    (7, "Gaurav Kumar", 84, "Chandigarh", "1998-07-06"),
    (8, "Sanket Jain", 61, "Shimla", "1990-09-08"),
    (9, "Sahil Wagh", 90, "Kolkata", "1968-04-03"),
    (10, "Saurabh Singh", 54, "Kashmir", "1989-01-06");
```
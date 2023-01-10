https://www.javatpoint.com/dbms-sql-aggregate-function


# SQL Aggregate Functions

SQL aggregate functions are used to perform calculations on multiple rows of a single column of a table. It returns a single value. It is also used to summarize the data.


## Types of SQL Aggregation Functions


### COUNT FUNCTION

COUNT function is used to count the number of rows in a database table. It can work on both numeric and non-numeric data types. COUNT function uses the COUNT(\*) that returns the count of all rows in a specified table. COUNT(\*) considers duplicates and Null.

```sql
COUNT(*)
or
COUNT( [ALL|DISTINCT] expression )
```

#### COUNT with WHERE
```sql
SELECT COUNT(*)
FROM PRODUCT_MAST;
WHERE RATE>=20;
```

#### COUNT with DISTINCT
```sql
SELECT COUNT(DISTINCT COMPANY)
FROM PRODUCT_MAST;
```

#### COUNT with GROUP BY
```sql
SELECT COMPANY, COUNT(*)
FROM PRODUCT_MAST
GROUP BY COMPANY;
```

#### COUTN with HAVING
```sql
SELECT COMPANY, COUNT(*)
FROM PRODUCT_MAST
GROUP BY COMPANY
HAVING COUNT(*)>2;
```


### SUM FUNCTION

SUM function is used to culculate the sum of all selected columns. It works on numeric fields only.

```sql
SUM()
or
SUM( [ALL|DISTINCT] expression )
```

#### SUM with WHERE
```sql
SELECT SUM(COST)
FROM PRODUCT_MAST
WHERE QTY>3;
```

#### SUM with GROUP BY
```sql
SELECT SUM(COST)
FROM PRODUCT_MAST
WHERE QTY>3
GROUP BY COMPANY;
```

#### SUM with HAVING
```sql
SELECT COMPANY, SUM(COST)
FROM PRODUCT_MAST
GROUP BY COMPANY
HAVING SUM(COST)>=170;
```


### AVG FUNCTION

The AVG function is used to calculate the average value of the numeric type. AVG function returns the average of all non-Null values.

```sql
AVG()
or
AVG( [ALL|DISTINCT] expression )
```

```sql
SELECT AVG(COST)
FROM PRODUCT_MAST;
```


### MAX FUNCTION

MAX function is used to find the maximum value of a certain column. This function determines the largest value of all selected values of a column.

```sql
MAX()
or
MAX( [ALL|DISTINCT] expression )
```

```sql
SELECT MAX(RATE)
FROM PRODUCT_MAST;
```


### MIN FUNCTION

MIN function is used to find the minimum value of a certain column. This function determines the smallest of all selected values of a column.

```sql
MIN()
or
MIN( [ALL|DISTINCT] expression )
```

```sql
SELECT MIN(RATE)
FROM PRODUCT_MAST;
```
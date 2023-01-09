https://www.tutorialspoint.com/what-are-the-most-used-sql-clauses-in-dbms


# SQL Clauses


## GROUP BY Clause

SQL GROUP BY is used to arrange identical data into groups. It is used with the SQL SELECT statement. The GROUP BY statement follows the WHERE clause in a SELECT and precedes the ORDER BY clause. It is also used with aggregation functions.

```sql
SELECT column
FROM table_name
WHERE conditions
GROUP BY column
ORDER BY column;
```


## HAVING Clause

It is used to search for a group or an aggregate. It is generally used in GROUP BY clause. If we are not using GROUP BY clause then we can use HAVING clause just like WHERE clause.

```sql
SELECT column1, column2
FROM table_name
WHERE conditions
GROUP BY column1, column2
HAVING conditions
ORDER BY column1, column2;
```

When GROUP BY is not used, HAVING behaves like a WHERE clause. The difference between where and having: WHERE filters ROWS while HAVING filters groups

```sql
SELECT SUM(spending) as totSpending
FROM militaryspending
HAVING SUM(spending) > 200000;
```


## ORDER BY Clause

This clause sorts the result in either ascending or descending order. By default, it does an ascending order if you don't mention anything. ASC and DESC are the keywords used to order the records.

```sql
SELECT column1, column2
FROM table_name
WHERE condition
ORDER BY column1, column2... ASC|DESC;
```
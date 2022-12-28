https://www.javatpoint.com/sql-update


# SQL UPDATE

SQL UPDATE statement is used to change the data of the records held by tables. Which rows are to be updated, it is decided by a condition. To specify condition, we use WHERE clause.

The UPDATE statement can be written in following form:
```sql
UPDATE table_name
SET column_name = expression
WHERE conditions;
```

### Updating Multiple Fields

If you are going to update multiple fields, you should separate each filed assignment with a comma.
```sql
UPDATE table_name  
SET field1 = new-value1, field2 = new-value2,
WHERE condition;
```

### SQL UPDATE WITH SELECT QUERY

We can use SELECT statement to update records through UPDATE statement.
```sql
UPDATE tableDestination
SET tableDestination.col = value
WHERE EXISTS (
    SELECT col2.value
    FROM  tblSource
    WHERE tblSource.join_col = tableDestination.Join_col
    AND  tblSource.Constraint = value
);
```

## SQL UPDATE with JOIN

SQL UPDATE JOIN means we will update one table using another table and join condition.

```sql
UPDATE table_name
SET
    table_name.column1 = other_table.column1,
    table_name.column2 = other_table.column2
FROM table_name
INNER JOIN other_table ON table_name.id = other_table.id
WHERE condition
;
```

## SQL UPDATE DATE

If you want to update a date & time field in SQL, you should use the following query.

```sql
UPDATE table_name
SET column_Name = 'YYYY-MM-DD HH:MM:SS'
WHERE condition
```
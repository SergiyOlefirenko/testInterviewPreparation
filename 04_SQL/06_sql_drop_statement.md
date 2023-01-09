https://www.w3schools.com/sql/sql_ref_drop.asp


# SQL DROP Keyword


## DROP COLUMN

The DROP COLUMN command is used to delete a column in an existing table.
```sql
ALTER TABLE Customers
DROP COLUMN ContactName;
```


## DROP a UNIQUE Constraint

To drop a UNIQUE constraint, use the following SQL:

**SQL Server / Oracle / MS Access**
```sql
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```

**MySQL**
```sql
ALTER TABLE Persons
DROP INDEX UC_Person;
```


## DROP a PRIMARY KEY Constraint

**SQL Server / Oracle / MS Access**
```sql
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```

**MySQL**
```sql
ALTER TABLE Persons
DROP PRIMARY KEY;
```


## DROP a FOREIGN KEY Constraint

**SQL Server / Oracle / MS Access**
```sql
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```

**MySQL**
```sql
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```


## DROP DEFAULT

This command is used to delete a DEFAULT constraint.

**SQL Server / Oracle / MS Access**
```sql
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```

**MySQL**
```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```


## DROP INDEX

Command is used to delete an index in a table.

**SQL Server**
```sql
DROP INDEX table_name.index_name;
```

**DB2/Oracle**
```sql
DROP INDEX index_name;
```

**MySQL**
```sql
ALTER TABLE table_name
DROP INDEX index_name;
```


## DROP DATABASE

Command is used to delete an existing SQL database.

```sql
DROP DATABASE testDB;
```


## DROP TABLE

```sql
DROP TABLE Shippers;
```


## DROP VIEW

```sql
DROP VIEW [Brazil Customers];
```
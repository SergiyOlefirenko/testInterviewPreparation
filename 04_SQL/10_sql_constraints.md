https://www.w3schools.com/sql/sql_constraints.asp


# SQL CONSTRAINTS

SQL constraints are used to specify rules for data in a table.

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the contraint and the data action, the action is aborted.

Constraints can be column level or table level. Column level constraints apply to a column, and table level contraints apply to the whole table.

The following contraints are commonly used in SQL:

- **NOT NULL** - ensures that a column cannot have a NULL value.
- **UNIQUE** - ensures that all values in a column are different.
- **PRIMARY KEY** - a combination of a **NOT NULL** and **UNIQUE**. Uniquelly identifies each row in a table.
- **FOREIGN KEY** - prevents actions that would destroy links between tables.
- **CHECK** - ensures that the value in a column satisfies a specific condtion.
- **DEFAULT** - sets a default value for a column if no value is specified.
- **CREATE INDEX** - used to create and retrieve data from the database very quickly.


## SQL Create Constraints

Constraints can be specified when the table is created with the **CREATE TABLE** statement, or after the table is created with the **ALTER TABLE** statement.

```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
```


## SQL NOT NULL CONSTRAINT

By default, a column can hold NULL value. The **NOT NULL** constraint enforces a column to NOT accept NULL values. This enforces a field to always contain a value, which means that you cannot insert a new record, or update a record without adding a value to this field.

### SQL NOT NULL on CREATE TABLE

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

### SQL NOT NULL on ALTER TABLE

**MS SQL Server**
```sql
ALTER TABLE Persons
ALTER COLUMN Age int NOT NULL;
```

**MySQL / Oracle (prior version 10G)**
```sql
ALTER TABLE Persons
MODIFY COLUMN Age int NOT NULL;
```

**Oracle 10G and later**
```sql
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```


## SQL UNIQUE CONSTRAINT

The **UNIQUE** constraint ensures that all values in a column are different. Both the **UNIQUE** and **PRIMARY KEY** constraints procide a guarantee for a column or set of columns. A **PRIMARY KEY** contraint automatically has a **UNIQUE** contraint. However, you can have many **UNIQUE** contraints per table, but only one **PRIMARY KEY**.

### SQL UNIQUE on CREATE TABLE

**MS SQL Server / Oracle**
```sql
CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

**MySQL**
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```

To name a **UNIQUE** constraint, and to define a **UNIQUE** constraint on multiple columns, use the following SQL syntax:
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT UC_Person UNIQUE (ID,LastName)
);
```

### SQL UNIQUE on ALTER TABLE

**MySQL / MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
ADD UNIQUE (ID);
```

Named or on multiple colums.
```sql
ALTER TABLE Persons
ADD CONSTRAINT UC_Person UNIQUE (ID,LastName);
```

### DROP a UNIQUE Constraint

**MySQL**
```sql
ALTER TABLE Persons
DROP INDEX UC_Person;
```

**MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```


## SQL PRIMARY KEY Constraint

The **PRIMARY KEY** uniquely identifies each record in a table. Primary keys must contain UNIQUE values, and cannot contain NULL values. A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

### SQL PRIMARY KEY on CREATE TABLE

**MySQL**
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```

**MS SQL Server / Oracle**
```sql
CREATE TABLE Persons (
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

To allow naming of a **PRIMARY KEY** constraint, and for defining a **PRIMARY KEY** on multiple columns, use the following SQL syntax:
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

### SQL PRIMARY KEY on ALTER TABLE

**MySQL / MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);

ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```

**Note**: If you use **ALTER TABLE** to add a primary key, the primary key column(s) must have been declared to not contain NULL values (when the table was first created).

### DROP a PRIMARY KEY Constraint

**MySQL**
```sql
ALTER TABLE Persons
DROP PRIMARY KEY;
```

**MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```


## SQL FOREIGN KEY CONSTRAINT

The **FOREIGN KEY** is used to prevent actions that would destroy links between tables. A **FOREIGN KEY** is a field (or collection of fields) in one table, that refers to the **PRIMARY KEY** in another table. The table with the **FOREIGN KEY** is called the child table, and the table with the **PRIMARY KEY** is called the referenced or parent table.

The **FOREIGN KEY** prevents invalid data from beign inserted into the the foreign key column, because it has to be one of the values contained in the parent table primary key column.

### SQL FOREIGN KEY on CREATE TABLE

**MySQL**
```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

**MS SQL Server / Oracle**
```sql
CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```

To allow naming of a **FOREIGN KEY**, and for defining it on multiple columns:

**MySQL / MS SQL Server / Oracle**
```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```

### SQL FOREIGN KEY on ALTER TABLE

**MySQL / MS SQL Server / Oracle**
```sql
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

To allow naming of a **FOREIGN KEY**, and for defining it on multiple columns:

**MySQL / MS SQL Server / Oracle**
```sql
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

### DROP a FOREIGN KEY

**MySQL**
```sql
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```

**MS SQL Server / Oracle**
```sql
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```


## SQL CHECK CONSTRAINT

The **CHECK** constraint is used to limit the value range that can be placed in a column. If you define a **CHECK** on a column it will allow only certain values for this column. If you define a **CHECK** on a table it can limit the values in certain columns based on values in other columns it the row.

### SQL CHECK on CREATE TABLE

**MySQL**
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```

**MS SQL Server / Oracle**
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);
```

To allow naming and for defining on multiple columns:

**MySQL / MS SQL Server / Oracle**
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```

### SQL CHECK on ALTER TABLE

**MySQL / MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
ADD CHECK (Age>=18);
```

To allow naming and for defining on multiple columns:

**MySQL / MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```

### DROP a CHECK

**MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
DROP CONSTRAINT CHK_PersonAge;
```

**MySQL**
```sql
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```


## SQL DEFAULT CONSTRAINT

The **DEFAULT** is used to set a default value for a column. The default value will be added to all new recoreds, if no other value is specified.

### SQL DEFAULT on CREATE TABLE

**MySQL / MS SQL Server / Oracle**
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```

The **DEFAULT** can also be used to insert system values, by using functions like **GETDATE()**:

```sql
CREATE TABLE Orders (
    ID int NOT NULL,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT GETDATE()
);
```

### SQL DEFAULT on ALTER TABLE

**MySQL**
```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
```

**MS SQL Server**
```sql
ALTER TABLE Persons
ADD CONSTRAINT df_City
DEFAULT 'Sandnes' FOR City;
```

**Oracle**
```sql
ALTER TABLE Persons
MODIFY City DEFAULT 'Sandnes';
```

### DROP a DEFAULT Constraint

**MySQL**
```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```

**MS SQL Server / Oracle**
```sql
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```


## SQL CREATE INDEX

The users cannot see the indexes, they are just used to speed up searching/queries. 

**Note:** Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

### CREATE INDEX

Creates an index on a table. Duplicate values are allowed.
```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);

CREATE INDEX idx_lastname
ON Persons (LastName);
```

### CREATE UNIQUE INDEX

Duplicate values are not allowed.
```sql
CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);

CREATE INDEX idx_pname
ON Persons (LastName, FirstName);
```

### DROP INDEX

**MS SQL Server**
```sql
DROP INDEX index_name ON table_name;
```

**Oracle**
```sql
DROP INDEX table_name.index_name;
```

**MySQL**
```sql
ALTER TABLE table_name
DROP INDEX index_name;
```
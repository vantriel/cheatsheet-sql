# SQL

[TOC]

## Database

### Create database

```sql
CREATE DATABASE testDB;
```

### Delete database

```sql
DROP DATABASE testDB;
```

### Backup database

```sql
BACKUP DATABASE testDB
TO DISK = 'filepath';
```



## Table

### Create table

```sql
CREATE TAB LE testTable (
    testID int NOT NULL,
    testName varchar(255)
    UNIQUE (testID)
);
```

### Delete table

```sql
DROP TABLE testTable;
```

### Delete data from table

```sql
TRUNCATE TABLE testTable;
```

### Alter table

#### Add column

```sql
ALTER TABLE testTable
ADD testDate date;
```

#### Delete column

```sql
ALTER TABLE testTable
DROP COLUMN testDate;
```

#### Modify column

```sql
ALTER TABLE testTable
MODIFY COLUMN testName varchar(128);
```



## Data

### `SELECT`

#### Select whole table

```sql
SELECT * FROM testTable;
```

#### Select  chosen columns

```mysql
SELECT testID, testName, testDate FROM testTable;
```

#### Select `limit`

```sql
SELECT testID, testName, testDate 
FROM testTable
LIMIT 256;
```

### `SELECT DISTINCT`

```sql
SELECT DISTINCT testID, testName, testDate
FROM testTable;
```

### `WHERE`

```sql
SELECT testID, testName, testDate
FROM testTable
WHERE testName='Mustermann';
```

### Operators

#### `AND`

```sql
SELECT testID, testName, testDate
FROM testTable
WHERE testName='Mustermann' AND testDate='2019-01-01';
```

#### `OR`

```sql
SELECT testID, testName, testDate
FROM testTable
WHERE testName='Mustermann' OR testName='Musterfrau';
```

#### `NOT`

```sql
SELECT testID, testName, testDate
FROM testTable
WHERE NOT testName='Mustermann' AND testName='Musterfrau';
```

### `ORDER BY`

#### `ASC`

```sql
SELECT testID, testName, testDate
FROM testTable
ORDER BY testName='Mustermann' ASC;
```

#### `DESC`

```sql
SELECT testID, testName, testDate
FROM testTable
ORDER BY testName='Mustermann' DESC;
```

### `UPDATE`

```sql
UPDATE testTable
SET testName ='Musterfrau'
WHERE testName='Mustermann';
```

### `DELETE`

```sql
DELETE FROM testTable 
WHERE testName='Mustermann';
```


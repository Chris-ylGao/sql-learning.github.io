## Theme: sql-learing
## description: mark down the nots and recods of sql

# 1.Manage data stored in a relational database 
## 1.1 Create a table
```ruby
CREATE TABLE tableName(
```
    // A list of parameters of each column, including name and datatype, eg: id INTEGER, name TEXT
    // For 'DATE' datatype, the format is 'YYYY-MM-DD'
```ruby
columnName1 DATATYPE1,
columnName2 DATATYPE2,
......
);

```
### 1.1.1 Constranint
Add information about how a column can be used are invoked after specifying the data type for a column. 
```ruby
CREATE TABLE tableName(
columnName1 DATATYPE1 PRIMARY KEY,
columnName2 DATATYPE2 UNIQUE,
columnName3 DATATYPE3 DEFAULT defaultValue,
columnName4 DATATYPE4 NOT NULL
);
```
    PRIMARY KRY: values of this column can be used as uniquely identifier;
    UNIQUE: values of this column should be different;
    DEFAULT: set defaultValue to this raws of this column if there is no statement;
    NOT NULL: column must have a value;
## 1.2 Insert a new row into a table

    // if the cloumn's datatype is TEXT, then value should be ''
```ruby
INSERT INTO tableName(columnName1, columnName2, ...)
VALUES(value1, value2, ...);
```
## 1.3 Add a new column to a table
```ruby
ALTER TABLE tableNmae
ADD newColumnName DATATYPE;
```
## 1.4 Fetch data from a table
    // fetch data of a cloumn in table
```ruby
SELECT columnName FROM tableName; 
```
    // fetch all data in table
```ruby
SELECT * FROM tableName;
```
### 1.4.1 SELECT statement
#### 1.4.1.1 AS
```ruby
SELECT columnName AS 'newColumnName'
FROM tableName;
```
    // rename column as "newColumnName"
#### 1.4.1.2 DISTINCT
```ruby
SELECT DISTINCT columnName FROM tableName;
```
    // filter the duplicate values of this column.
#### 1.4.1.3 WHERE
```ruby
SELECT columnName FROM tableName
WHERE condition;
```
    // Basic condition symbol
       =: equal to
      !=: not equal to
       >: greater than
      >=: greater than or equal to
       <: less than
      <=: less than or equal to 
#### 1.4.1.4 LIKE
```ruby
SELECT columnName FROM tableName
WHERE columnName LIKE 'specialPattern';
```
    //Fetch values with similar pattern;
       _:  can be substituted any individual character
      A%: begin with A
      %a: end with a
    %ab%: contains ab
#### 1.4.1.5 IS NULL/IS NOT NULL
```ruby
SELECT columnName FROM tableName
WHERE columnName IS NULL;
```
```ruby
SELECT columnName FROM tableName
WHERE columnName IS NOT NULL;
```
#### 1.4.1.6 BETWEEN
```ruby
SELECT columnName FROM tableName
WHERE columnName BETWEEN value1 AND value2;
```
    // When value's data type is an int, [value1, value2], value2 is included;
       When value's data type is text, [value1, value2), value2 is not included.
#### 1.4.1.7 AND/OR
```ruby
SELECT columnName FROM tableName
WHERE condition1 AND ondition2;
```
```ruby
SELECT columnName FROM tableName
WHERE condition1 OR condition2;
```
#### 1.4.1.8 ORDER BY
```ruby
SELECT columnName FROM tableName
ORDER BY columnName ASC/DESC;
```
    //ASC: A-Z
      DESC: Z-A
      Default is ASC.
#### 1.4.1.9 LIMIT
```ruby
SELECT columnName FROM tableName
LIMIT number;
```
    //Set the max number of results
#### 1.4.1.10 
```ruby
SELECT columnName,
CASE
WHEN condition1, THEN value1 
WHEN condition2, THEN value2
......
ELSE valueN
END AS 'newColumnName'
FROM tableName;
```
    //According to conditions, create a new colmun named "newColumnName"
## 1.5 Add a new column to a table
```ruby
ALTER TABLE tableNmae
ADD newColumnName DATATYPE;
```
## 1.6 Edit a row in a table
```ruby
UPDATE tableName
SET updateColumn = newValue
WHERE column = value;
```
    // WHERE is to locate the row*
## 1.7 Delete a raw or rows from table
```ruby
DELETE FROM tableName
WHERE column IS value;
```
# 2. Perfrom calculation in sql
## 2.1 Count
    //count the number of rows in a columan
    //if want to count whole rows in the table, than set columnName as "*"
```ruby
SELECT COUNT(columnname)
FROM tableName
WHERE condition
``` 
## 2.2 SUM
    //return the sum of all values in a column
    // if the data type of value is not interger, then return 0.0
```ruby
SELECT SUM(columnName)
FROM tableName;
```
## 2.3 MAX/MIN
    //return the maximum/minimum value of colomn
```ruby
SELECT MAX(columnName)
FROM tableName;
```
```ruby
SELECT MIN(columnName)
FROM tableName;
```
## 2.4 AVG
    //get average of values of sepcific column
```ruby
SELECT AVG(columnName)
FROM tableName
```
## 2.5 ROUND
    //round the values in the column to the number of decimal places specified by the integer
```ruby
SELECT (columnName, integer)
FROM tableName;
```
## 2.6 GROUP BY
    // The "GROUP BY" statement comes after any "WHERE" statements, but before "ORDER BY" or "LIMIT".
```ruby
SELECT columnName1, columnName2, Method()
FROM tableName
GROUP BY columnName1;
```
    // GROUP BY can use reference number intead of columnName
```ruby
SELECT columnName1, columnName2, Method()
FROM tableName
GROUP BY 1;
```
## 2.7 HAVING
    // HAVING is similar to WHERE; 
    // When limiting the values of the individual rows, use WHERE; When limiting the results of a query based on an aggregate property, use HAVING.
    // "HAVING" statement always comes after "GROUP BY", but before "ORDER BY" and "LIMIT".
```ruby
SELECT 
FROM
WHERE
GROUP BY
HAVING
ORDER BY
LIMIT;
```
# 3.Mutipile tables
## 3.1 Combine tables
### 3.1.1 INNER JOIN
    //Add column of table1 to table2, accoring to "condition".
    // columnNamr = *, if you want to add all table1 to table2
    // can also use "WHERE" statement to set condition of table
```ruby
SELECT columnName FROM tableName1
JOIN tableName2
ON condition;
```
### 3.1.2 LEFT JOIN
    //reserve all rows in the table1, and add table2 according to "condition"
```ruby
SELECT columnName FROM tableName1
LEFT JOIN tableName2
ON condition;
```
### 3.1.3 CROSS JOIN
    //combine all rows from table1 and all rows from table2
    //CROSS JOIN without ON condition
```ruby
SELECT columnName FROM tableName1
CROSS JOIN tableName2
```
### 3.1.4 UNION
    //stack table1 on the top of table2
    ```ruby
    SELECT * FROM tableName1
    UNION
    SELECT * FROM tableName2;
    ```
## 3.2 WITH
    //create a temporary table
```ruby
WITH temporaryTableName AS(
....
)
SELECT ...
FROM temperaryTableName
......;
```

[x]

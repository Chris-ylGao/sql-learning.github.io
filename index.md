## Theme: sql-learing
## description: mark down the nots and recods of sql

# 1. Create a table
```ruby
CREATE TABLE tableName(
```
    //a list of parameters of each column, including name and datatype, eg: id INTEGER, name TEXT
```ruby
columnName1 DATATYPE1,
columnName2 DATATYPE2,
......
);

```
## 1.1 Constranint
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
    UNIQUE: the values of this column should be different;
    DEFAULT: set defaultValue to this raws of this column if there is no statement;
    NOT NULL: column must have a value;
# 2. Insert a new row into a table

    // if the cloumn's datatype is TEXT, then value should be ''
```ruby
INSERT INTO tableName(columnName1, columnName2, ...)
VALUES(value1, value2, ...);
```
# 3. Fetch data from a table
    // fetch data of a cloumn in table
```ruby
SELECT columnName FROM tableName; 
```
    // fetch all data in table
```ruby
SELECT * FROM tableName;
```
# 4. Add a new column to a table
```ruby
ALERT TABLE tableNmae
ADD COLUMN newColumnName DATATYPE;
```
# 5. Edit a row in a table
```ruby
UPDATE tableName
SET updateColumn = newValue
WHERE column = value;
```
    // WHERE is to locate the row*
# 6. Delete a raw or rows from table
```ruby
DELETE FROM tableName
WHERE column IS value;
```

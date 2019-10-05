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
# 2. Insert a new row into a table
```ruby
INSERT INTO tableName(columnName1, columnName2, ...)
VALUES(value1, value2, ...);
```
    // if the cloumn's datatype is TEXT, then value should be ''
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
# 6. 

# SQL Query

## Clone a new table from another table

> SELECT * INTO WorkerClone FROM Worker; (including data)

> CREATE TABLE WorkerClone LIKE Worker;

> SELECT * INTO WorkerClone FROM Worker WHERE 1 = 0;

## Nth salary 

> SELECT Salary FROM Worker ORDER BY Salary DESC LIMIT n-1,1;

`SqlServer`

```
SELECT TOP 1 Salary

FROM (
 SELECT DISTINCT TOP n Salary
 FROM Worker 
 ORDER BY Salary DESC
 )
ORDER BY Salary ASC;
```

## list of employees with the same salary.
```
Select distinct W.WORKER_ID, W.FIRST_NAME, W.Salary 
from Worker W, Worker W1 
where W.Salary = W1.Salary 
and W.WORKER_ID != W1.WORKER_ID;
```

## the last record from a table.

> Select * from Worker where WORKER_ID = (SELECT max(WORKER_ID) from Worker);

## Looping

```sql

Declare @id id
Declare @name varchar(100)

Declare table_cursor select * from TableName
    OPEN table_cursor
    FETCH NEXT FROM table_cursor into @id, @name
WHILE @FETCH_STATUS = 0
BEGIN
    Print 'Id =' + coalesce(convert(varchar(10), @id, 0),'0') + 'Name:' + @name
    FETCH NEXT FROM table_cursor into @id, @name 
END
CLOSE table_cursor
DEALLOCATE table_cursor
```
## Execution Plans
    An execution plan provides a graphical representation of how the query optimizer chose to execute a query
[See Optimization technique](https://www.sqlshack.com/query-optimization-techniques-in-sql-server-the-basics/)
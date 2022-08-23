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

## Execution Plans
    An execution plan provides a graphical representation of how the query optimizer chose to execute a query
[See Optimization technique](https://www.sqlshack.com/query-optimization-techniques-in-sql-server-the-basics/)

## What is SQL and why SQL	
What is SQL, which is abbreviated from Structure Query Language.  Sql is a non-procedural language used to get information from relational databse for convenience. 

## select from where

Select ... from ... where ... is the most famous statements in the SQL. 

Actually, when we write a table, we need to consider where to get the data.  so we should firstly  consider the from clause.  

- we can get data from a single table
- we can also get data from two table, such as from table1, table2. We may even use more than 2 tables. 
- we can also get data by join (or left joi), such as from  A join B on(A.ID = B.ID). We may even use more than 3 joins. 
- we can also get data from a virtual table by subquery ( this can usually be used to problem about aggregation)


## Aggregation

Aggregation is very common in the real-life application. For example, if we wnat to get max, min, avg, or sum of the data, we need aggregation function.

The aggregation function that the sql provides are max, min, avg, sum, count, std, count(distinct). 

When we use aggregation function, we usually use keyword  group by. 

When using group by, we can use having to do some filter operations. 

## scalar subquery
What is scalar subquery? Scalar subquery is a sql subquery with a return that only has one row and one column.

Scalar subquery can be used to select clause or where clause.  It can be used to select clause to be as a single filed, or used in where clause to be a  condition. 




 


## What is relational data model.

Relation is nothong more than a table.  Relational database is row oriented. The row can also be called the tuple. And the tuple is composed by the n number of attributes. Each attribute can also be called column.


Actually, relational model is very intuitive and simple, and easy to understand.   

From mathmatical perspective, I think relation model is nothing more than a set. Each table is a set, and we can define operations on the one set or more than two sets.

## Key

As we can understand relational database as a set, each element in the set is distinct. So in the relational model, it is also required each row to be distinct. So we have the primary key for the table.

The primary key is a set of attributes, which can be used to make each row distinct.

## Relational operations

As we need to do some queries on the data, so we need to define some operations on the data. Actually, the famous mysql is based onthe relaional operations. So how many operations we can deine to satisfy different query requirements. 

1. Selection 
2. Projection
3. Cartesian product
4. Natural Join
5. Union, intersection, difference

Usually, this five operations can be used to any queries.

If we want to do search on a single table, selection and projection is enough.

If we want to do search on the multiple tables, we have to use natural join or cartesian product. Actually, natural join is very useful in joining two tables having the same value on the attribute with the same name. 

If natural join can't finish the search of two tables, we can use Cartesian product, which is more felxible. 

## Relational operations and SQL

SQL is abbreviated from Structured Query Language.


The formal definition of query is  select some attributes from some tables where some constraints must be met.

1. from clause. We can get data from  one or more than two tables. If we get data from more than two tables, it is nothing more than Cartesian product or natural join operations.  We can use either Cartsian product or natural join to get the information

2. where clause,  where clause is implemented by selection operation. 

3. As for select clause, which is implemented by projection operatiob.

In total SQL is nothong more than relational operations, what we need to do is to translate sql to the relational operations, and then optimized based on the relational operations and indexs. 

Overview of relational database concept and relation. 

Give a global overview of it, so I can study and understand with efficiency.

How to understand relation, a relation is a table. And we can define relational algebra for query operations.  Relational algebra is a theoretical fundamental for relational databse.
 
Relational is an internal representation of query operations, but it is not user-friendly, so there is another language called SQL, which can be converted to relational algebra.  There are three basical forms of SQL.

- select ... from ... where ...
- select ... from ... where ... group by 
- nested subquery

Since we have a concept of what is relational databse , right now the question is how to design a relational databse.  We have two theorems to support database design. One is E-R model, another is normal form for redundancy elimination. 

E-R model is a logical model to present the entities and relationships of entities. Entity can be any object, relationship descripes the relationship among entities. 

As for normal form, which is used to elinminate redundancy. Why we need to elinminate redundancy. That is because when we do some updations, if there are many redundancy data we need to update, there is a high risk of data inconsistency because we may forget to update the redundant data concurrently. 

There are basically three kinds of normal form as following 

- the first normal form is simple, which requires each attribute should be atomic 
- the sec normal form is a bit complex, which is based on functional dependency. It requires, for each functional dependency in the relation alpha -> beta, alpha should be superkey.
- The third normal form is a relaxed version of the second normal. 


The normal form is based on functional dependency theorem.  We can use funcitonal dependency theorem to elinminte the redundancy. 

IF a relation is not BCNF(sec normal form), we can use algorihtm to automatically to split the relation into more than 2 relaitons , which are all  BCNF.  

After introducing the concept the relation and the design of database , we should also care about how to implement such a databse and what is the details for database implementation. 

Details of physical storage.  The data is stored on the physical storage, so we need to understand physical storage.

- cache
- main memory
- flash memory
- magnetic disk
- DVD 
- tape

The cache is the fastest. And then main memory, but both is vonlatile, which means the data disappears when power off.  As for flash memory and magnetic disk, both is frequently used in database. Actually magnetic disk is the most frequent use because it is cheaper than flash memory, but flash memory has an advantage of performance than magnetic disk.


As the magnetic disk is frequent used , we are going to explore more details about magnetic disk. 

The composition of magnetic disk, there are serveral platter of disks, and each platter is composed by multiple tracks, and each track is composed by multiple sectors. 

Sector is the basic unit of storage in disk. 

And then read-write head arm is used to postion to a specific track and then read or write data. 

The performance of disk

There are three metrics to evaluate disk, seeking time, data transfer time and reliability. 

- Seeking time, postion the read-write head to specific track, and then rotate to specific sector of the track.
- Transfer time, dependends on the data transfer rate from disk to memory and memory to disk.
- reliability, the average mean time of disk to lose data or fail.  This can be solve by redundancy storage of data. 


Flash memory

Flash memory is also a non-volatile memory, which is faster than magnetic disk. 

The write for flash memory is  a bit complicated, the data must be firstly erased, and then can be over-written.   We can solve this problem by mapping of logical blocks to physical blocks. 


Since we have talked about the physical storage, we are going to talk about how the record is stored in the physics.

There are to ways to organize records. 

First way is to oraganize records with fixed length.

Another way is to organize records with variable length. 

But how to organize records

- heap file organization, just like appending log, and then matain a free-list of available space
- sequential file organization, search key is maintained in order, and we can use linked list to implement it 
- hash file organization
- multitable organization, multiple relations are stored in the same file 
- B+ tree file organizaiton, a efficient organization. 

B+ tree is the most frequent used one because it has a very good time complexity of query, insertion, deletion and updation. 


After we know how the records is arranged and how the file is organized for storing in the databse, we are going to talk about index to fasten query performance. 

Index can be classified into dense index and sparse index. Dense index and sparse index has a trade-off between space and query performance.


Sure, there are other index structure, the most famous one is B+ tree index structure, and another is hash index structure then bitmap index structure.


Has index structure is efficient for equality query, as for B plus tree index structure it can be used to not  only for equality query but also for range query. As for bit map index, which is used for query like the data of  Male and Female. 


Another index is secondary index, scondary index is a index that the search key is not primary key. 


After talking about the index, I am going to talk about how the sql query is converted into the interal representation of algebra expression, and then we can optimize the algebra expression to improvce the query efficiency.

This is the process of query processing.

1. Convert sql to realtion expression by compiling and parsing
2. Optimize the reltion expression to generate execution plan
3. Execute the plan by execution engine. 


For selection, there are multiple algorithms to execute, but which algorithm is best?  And how we measure each algorithm.

We can measure a algorithm from these metrics.

- The number of seeking 
- The number blocks needs to be transferred
- the CPU exectuion time.
 
Usually the CPU execution time is faster than seeking and block transfer time, so we only consider the seeking time and transfer time .



Usually the CPU execution time is faster than seeking and block transfer time, so we only consider the seeking time and transfer time .


Algorithms for slection on a relation

1.  brute force, linear scan,  simple but inefficient

2. Selection based on index, there are two conditions

2.1 Conjunctivce form

The form like a1 and a2 and ... and an

One method is to filter a relation with an atrribute having an index. 

Another method is to make full use of each index and then do intersection operations.

2.2 Disconjunctive form

The form like a1 or a2 or ... an

We can use index search only when each ai has an index; otherwise, we have to use linear scan.

Algorithms for selection on more than one relation

Usually, we need to query on more than one relation, the most common one is natural join.

What is the algorithm for natural join? 

1. Brute force- two-nested loop

Get the blocks of realtions and then comppare pair of blocks.

2. modified two nested loop

If one relation is small, so we can load that relation into the memory. 

3. One loop based on index

we can linear scan a relations and then search on another table based on index. 

4. hash partion 

We can hash the two rlationsh into partions, and then compare the data in the partions, this is a idea of divide and convquer. 


Materialized query

As the algebra expression may produce intermideate realtion, so we need to write it into the disk, the process of which is called materializtion. 

However materialization is expensive, it cost extra read and write time 

So another solution is pipeline.


Pipeline

the intermediate output can be used for next subexpression input, so we don;t need to store the intermediate result.

Stream pipeline

Sometimes the intermediate output is too big to be hold in memory, so we don't need to wait until all the intermidete is ready. We can deal with realtion tuple one by one just like a stream. 

Until now we have talked about the algorithms for dealing with query, and the algorithm performance. 

Right now we are going to optimization of query processing.


Optimiaztion

The optimization of query lies in the fact that given a relation expression, we can get many other equivalent expressions, but which one expression is best for the performance.

So the first way is that we need to find all the equivalent expression.  So we need to define equivalent rules. 

How we measure the expression is good or bad?  The size of tuples we need to query can be a metric for specific expression.

How we get the size of tuples, one way is that we can think each attribute is uniform distributed

Another way is that we need maintain the statistics of each attrabute, so we can get distribution of each attribute from statistic attribution. 

If we maintin the statistic of relation accurately, it is very expensive ,we can maintain approximately. 

And it is also impossible to compute all the equivalent algebra expression, so we may only compute part of good equivalent expression, that is we can use heuristic.

Heuristics 

1. Selection as soon as possible
2. Projection as soon as possible


Transaction management 

Transaction is very important in relational databse.  But what is transaction, transaction has four important properties.

1. Atomiciy, either all done or no done
2. Durability, Once transaction commites, the data will be persistent.
3. Isolation, allows concurrent transaction execution, which means intermediate updation of a transaction can not be see by any other transaction.
4. Consistency, from the application perspective, after transaction execution, the data is always in consistency. 

How to implement a transaction.

As for atomicity, we can implement by log, we use log to persistent each updation. When the transcation is commited, we guaranttee that the log will be persistent, if the transaction is rollback, we guaranttee that the updation will be rollback , so we need to know the old version data before updaton, all this can be done by transaction.


As for durability, it can be implented together with atomicity by using log, so log is very important in realtional databse of transaction implementation and failure recovery  and replication.


As for isolation, this is very complex implementation of transaction, we need cucurrency control of mutilple concurrent transactions, so we need concurrent control system. 

Some schedule of transaction can cause a bad result, while some scheduler of transaction can produce a good result. Let's consider the simplest one, if the transaction is implemented by 


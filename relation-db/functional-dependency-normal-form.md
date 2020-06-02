
## What is functional dependency

alpha -> beta, we call beta is functional dependent on alpha on relation r, that is if alpha1  equals to alpha2, beta1 also equals to beta2. 

In other words, the value of alpha determines the value of beta, or the value of beta is determined by alpha. 

Actually functional dependency is also a kind of constraint in relational database design. 

## Why functional dependency

Functional dependecny can also be used to detect redundancy. Why it can detect redundancy?  

I can list a example. Let alpha-> beta be a functional dependency.  And alpha is not a primary key

So there exists two tuples t1 and t2 with alpha1 equaling to alpha2 and beta1 equaling to beta2.  So t1 and t2 are redundancy data.

So we need to get all the functional dependency , and then ensure each functional dependency alpha-> beta. alpha is primary key,  so the relation will not have a redundant information. 

## Why we eliminate redundancy. 

More redundancies in relation, more risk of data inconsitency. In another view, reduce redundancy can reduce the size of storage. 

## Normal form and functional dependency

Normal form is used to design the relational database.  There are basical three normal form .

### The first normal form

This normal form is very simple, each attribute of the relation is atomic.

### The second normal form

For each f denoted as functional dependency in a functional dependency set F,

f must satisfy the following conditions

1. alpha -> beta, beta is subset of alpha
2. alpha is primary key 

This scheme is called  BCNF

### The third normal form 



## Functional dependency theorem. 

alpha-> beta denotes a functional dependency.

 

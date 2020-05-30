
### relation algebra.

Relation algebra is theretically used to the realtion query operations. It is the fundamental theorem to sql query. 

I think relation algebra is very nice, at first, we can define operations to make the query felxible ,actually the necessary operations are only  small part, but these operations can satisfy all kinds of sql query. What an amazing.

And relation algebra is closed under its operations, which means relation algebra uses relation as a basic unit for operations, that is relation algebra accepts realtion as input and also ouput relation. It is beautiful, just like arithmetic, it is basic element is number, and input is number , output is also number.

### Relation And operations
Relation refers to table in relational database.

Basic operations

- Selection 
- Projection
- Cartesian Product
- Rename 

These are three basic operations, and it can satisfy all kinds of sql query.  

Selection and projection are unary operations, Projection is used to select atrributes. Selection is used to filter the tuples. And Cartesian product is very useful in multiple relations query. Rename is auxiliary operation used to distinguish relations for multiple table query.  

Extended operations,  there are some other operations can be inducted from the above three basical operations, for example, natural join, which is very important in multiple data query.

#### Natural join
Natural join is joining the two tables with the same atrribute with the same value. We can combine selection and cartesian product to get the natural join.  But natural join can be used for simplicity .

#### Join
Natrual join has to compare all the attributes with the same name, but sometimes we only need to compare part of attributes with the same name, so we can have join, which is more flexible than natural join.

#### Left join, right join and full join.
There is a condition that some tuples are filtered out if we only use join, but we want the tuples of relation to the left of join are all included, so we can use left join here. 

### Aggregation
There is another operation that is very imporatn for statistics analysis, such as min, max, avg, sum, count. So we need to support aggregation.   


## Tuple relational calculus

Relation algebra is used for relation operations, but there are some other operations, which has the same function with relation algebra, tuple relation calculus is another one. 

Tuple relational calculus is based on set theorem and logic theorem.  The general form is 

{t | P(t)}, P(t) is a logical formula used to express the characteristics of t. 

The tuple relational calculus is equivalent to relation algebra. So we can use tuple realtion calculus to express operations in relation algebra.

- selection,   {t | t is in instructor and t[salary] > 1000}      
- projection, {t | exist s in instructor(s[ID] = t[ID] and t[salary] > 1000)}
- cartesian production, {t | exist p in instrucotr exist q in instructor([t[ID] = p[ID] and t[student_name] = q[student_name])}

## Domain relational calculus 

Domain relational calculus is very similar to tuple relational calculus. The basic unit in tuple relational calculus is tuple, but the basic unit in domain relational calculus is domian. And tuple can be composed by n-domains. Actually, I think domain relational calculus is more flexible than tuple relation calculus, but domain relational calculus is equivalent to tuple relational calculus.

A formal expression of domain relational calculus 

{ <x1, x2, x3 ... xn> | P(x1, x2, x3 ... xn)}

- selection {<x1, x2, x3 .. xn> | <x1, x2 ... xn> is in table instructor and x2 > 1000}
- projection {<x1, x2> |  <x1, x2 ... xn> is in table instructor and x2 > 1000}
- cartesian production, {<x1, x2,x3 ... y1, y2, y3> | <x1, x2 ,x3> is in table instructor and <y1, y2, y3> is in table stduent}


## Conclusion

What I can learn from relation algebra is that we can define basic research object, which is relation here. And then define relation algebra, that is relation operations. Basic on relation operations, we are able to query all the necessary information from database scheme, what an amazing.

And we also know that sometimes there are more than one definition that can express the same thing, which also amazes me. Here relation algebra, tuple relational calculus  and domain relational calculus are equivalent. 


 

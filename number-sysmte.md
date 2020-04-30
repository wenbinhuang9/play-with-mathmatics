
### What is the natural number?

The natuaral number is 0, 1, 2,3 ..., this definition sounds good, but what is infinity.

This is a definition of natural number.

Axiom 1. 0 is a natural number
Aximo 2. n++ is also a natural number

But what is n++, we define n++ to be an increatment operations, so we define 1 is 0++, 2 is (0++)++, 3 is ((0++)++) , and so on. 

The problem of this definition, what if we can make (n++) is 0. This problem exist in the real life. 16 bit interger in computer is 65,536, but when 65,536 + 1, it is calculated to 0. 

so, A contsraint is added to the natural number:

Axiom 3. 0 can not be the successor of any natural number, that is n++ != 0

We have limited the 0 not be the successor of any natural number , but it is still possible that 1 may be the successor of any other natural number, so another constraint is going to add to the natural number, that is:

Axiom 4. Two different natural number can not have the same successor, that is if n!=m, n++!=m++

Based on this axiom, we can prove  2 != 4
Assume 2 equals to 4 for the sake of contracdition, so 1++ = 3++, 0++ = 2++, 0 = 1++, contradicting the n++ != 0

Until now, we have defined what is natural number, but there is still a question that we still not exlcude the number that is not natural number. For example

the number set = {0, 0.5, 1, 1.5, 2, 2.5, 3, 3.5 ...}

How we solve this, we should find a property such that that property is only belonging to the natural number.

Axiom 5, If n is a natural number, P(n), the property pertaining to the natural number is true. 

That is if some number m and P(m) is false,  then  m is not a natural number.

Axiom 6, we can find such a property that makes P(n) only true for all natural number.

But how we find such a property. This is a property we canuse, that is given a number, n is natural number. we can prove the property by induction.

(1) when n is 0, P(0) is true, because 0 is natural number(2) Assume n is natural number, P(n) is true
(3) As for n++, n++ is natural number because n is natural number, so P(n++) is true.

So until now, we all done the definition of natural number. If you look carefully, we don't try to define what is natural number, all the contraints we define is the property of natural number. This is what mathmactics do to search the abstract object, and we care about the property the object. And we also care about the operation of the object. That is addition , multiplication , minu and division in natural number. So we are going to define what is addition.



### What is the addition of natural number?

We define the addition, let m be a natural number 
0 + m = m
Suppose we have defined m adding to n denoted by n + m,
and so we define inductively that (n++) + m = (n + m)++ 

Prove m + 0 = m

we can prove it by induction




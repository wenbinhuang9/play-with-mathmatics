
The complexity theory cares about when there is a algorithm to solve a problem,  how much time and spaces we need to compute the problem. 

And how to measure the time complexity? we measure the time complexity by the order of operations. What is operation? Operation is the basic comput unit. Polynomial order is the key in the time complexity analysis. 

### Definition of P class.

The formal definition is based on the one-tape deterministic TM,  P is the class of the language decidable in polynomial time on that kind of TM. 

In other words ,there is a polynomial solver for the problem. 

Why use polynoimial to define the P class ,I think this definition is based on the experience of most solvable problems in realistic computer is polynomial. And actually, polynomial is very useful in this definition. 

### Definition of NP class

Now we have came a famous problem in complexity theory, that is NP problem. 

What is defintion of NP problem? 

The definition of NP relies on decision problem, so what is decision problem. 

The decision problem is that kind of problems only having true or false answer.

And we can find proof of yes instance of the problem  is yes instance, which is called certificiate.

If we can find a polynomial verifier for the certificate ,that kind of problem is in NP class.


Actually, this definition is equivalent to that a problem can be solve by a non-deterministic TM in polynomial time.


### Definition of NP-completeness.

For informal definition, NP-complete is the hardest problem in the NP. But how to descript hardest? 

Yes, we can also use reducibility here to descript hardest here.

A problem is called NP-complete when all the NP problems are reducible to that problem, which means the problem is at least harder than all the NP problems. 

And SAT is the first NP-complete problem being proved.

And the proof of other NP-complete problem usually make SAT reduciable to that problem. 

### Proof of SAT is NP-complete

Actually, this proof is very hard, because it is the first NP-complete problem to prove.

Try to think about this beautiful proof.


### other NP-complete problem 

vetex-cover, clique, halmiltonion circuit,  travel salesman problem, independent set, subset sum , knacksack problem.

Todo familiar with this kind of problems reduction. 

### the relationship of all this problem class.



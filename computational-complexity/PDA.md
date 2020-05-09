### what is PDA or BNF? 

a^nb^n can not be expressed by regular language, are there any powerful computational model. Yes , PDA is a powerful machine, and context-free language can be expressed by the PDA. 


#### definition of CFG

Four tutples to define the CFG

- V: set of variables
- S: set of symbols, epsilon included
- P: productions with the form V1 -> U1U2U3, where V1 is a variable string, and U1U2U3 .. is either a variable or symbols. 
- s0: the start variable

CFG can be used to describe human languages, but it usually broadly used in programming language design.

And the simliest thing we can do is to use CFG to define a regular language grammar.

#### definition of PDA

PDA is equivalent to CFG, CFG is a generator, but PDA is a simulator. PDA has a unlimited stack as memory, so PDA is more powerful than DFA. 


- s0: start states
- F: accept state 
- Q: set of states
- S: input symbols 
- T: tape symbols
- P: transition function with the form f(r1, a, k1)->(r2, k2), where r1, r2 are states, and a is input symbol, while r1 is the element on the stack top, and k2 is a symbol wil be put into the top of stack.

The stack of PDA only supports push and pop. The powerfulness of PDA lie in that it can matches the number of symbols, such as matching the numbers in palindrome. 


### equivalence of PDA and CFG

#### converting CFG to PDA

It is surprising that PDA and CFG are equivalent.

Right now, I am going to talk about converting CFG to PDA. We allow variables in the stack, so when a variable is met in the stack, the variable can be popped , and its right hand rules can be put into the stack.  

When it is a terminal on top of stack, just make it matched with the input symbol.


#### converting PDA to CFA

As for converting PDA to CFG, it is a little complex. Let qi, qj be the two states of PDA, let Aij be a variable of qi, and qj. Aij means all the strings going through Aij will also go through qi and qj.


So there are three basic conditions to convert PDA to CFG.
(1) Aii -> epsilon 
(2) Aij -> aArsb when there is two transition function from f(i, a, epsilon)-> (r, k) , f(s, b, k)->(j, epsilon) 
(3) For each p, q, r , put the rule Apq -> Apr Arq

This process's proof can be done by the induction. 



### Closure of PDA and CFG

#### closed under union

simple to prove by unioning two CFGs.

#### closed under concatnenation

simple to prove by concatenating two CFGs.

#### closed under star

simple to prove by adding a new rule for the start state by S-> SS

#### not closed under intersection

The classical counter example is use a^pb^qc^s, where p = q, and a^pb^qc^s, where q = s.

#### not closd under completement.

What's the counter example here ??? There must be a counter examle .

### Computability

#### {(PDA w) | PDA accepts w}

This proof is converting CFG to a chomsky normal form , and then for each word with length n, can be found in the 2n-1 steps, so find all the words with 2n - 1 steps, if w is in the set,accept; otherwise reject.

#### {PDA | PDA is empty set}

This can be proved by using DFS

1. Mark any terminals
2. Repeat until no new variables marked
	2.1 For each rule, S->U1U2 .. Uk, mark S if Ui marked for each i
3. If S is marked, accept; otherwise, reject.

#### {(A1, A2) | A1 and A2 is CFG, and A1 equals to A2}

Actually, this is not a decidable problem. CFG is not closed under intersection, so we can not convert this problem to empty set decidability problem. 

#### {A1 | A1 is CFG and A1 accepts at least 3 strings}
My idea is to convert it to chomsky normal form, and then we can know that the maximum number of strings, and


### Undecidability of CFG

There are some problem undecidable in CFG

1. Given CFG, accept everything?
2. Given CFG, is it ambiguous?
3. Given two CFGs, are these two equals?  


### Pumping lemma

Is there the language that is not CFG. If it is not, how we prove that. Similarly to DFA's pumping lemma, we can also find the pumpling length for the CFG.

Similarly, we can find a string with a very long length, and one of variables must be repeated, so we find a repetitive pattern in the rules. 

So the repetitive pattern has thoes three characteristics as follows

Any s in the language can be divided into five parts, uvxyz

1. |vxy| <=p
2. |vy| > 0
3. uv_ixy_iz is also belonging to L. 







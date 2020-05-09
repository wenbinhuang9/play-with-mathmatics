
### what is DFA

DFA deterministic finite automata, this is formal definition as follows,

A DFA is a five tuple(s, B, Q, E, T)

- B: a finite set of input symbols called the alphabet B
- Q: a finite set of states
- F: a set of accepting states, F is subset of Q
- T: A transition function Q * B -> Q
- s: a start state , where s belongs to Q


#### Definiton of accepting and regular languages

we have a DFA M, and a string w= w1w2w3...wn, where wi belongs to input symbols of M.

We define M accepting w only when we can find q0q1q2 .. qn, where qi belongs to states of M ,such that three conditions are met. 

1. q0 = s
2. f(qi-1, wi) -> qi
3. qn belongs to accepting states F.  

And we define regular languages by L = {w | M accepting w, M is a DFA}, which means if a language is regular, we can find a DFA to recognize it.

#### Definition of regular operations

1. Let A and B be regular  languages

- Union: A or B
- Concatenation: A.B = {xy | x is in A or x is in B}
- Star:  A * = {x1x2 .. xk | k >=0 and each xi is in A}


If A1 and A2 are regular languages, A1 or A2 is regular languages too. 

one proof solution

we can define by adding a epsilon transition, then building NFA (but we need to define NFA), and then construct NFA by adding a new start state and a final state, then connect this new state to start state of M1 and M2, connect final states of M1 and M2 to the new final state.

2. Let A be a regular language, A * is also a regular language.

Similar as above, construct a DFA by adding a epsilon transition from final state to start state. 

3. If A1 and A2 are regular languages, A1 . A2 is also regular language. 

One proof method is going to building NFA by adding epsilon transition  from accept state of M1 to start state of M2, and then transit NFA to DFA.


#### Closure Properties

1. The DFA is closed under complementp

Intuitive proof, replace the accept state to non-accept state, and replace non-aacept state to accept state. 

Formal proof

Let M be a DFA, and let Q be the states of M, and F be the accepting states of M, we construct a DFA buy switching accept state to non-accept state, and switch non-accept state to accept state, so the accepting state M' is Q - F.

Assume w=w1w2w3 ... wn is accepted by M, and its state sequences is q0q1 ..qn, where q0  = s and qn belongs to F, w will be rejected by M' because the qn is not belonging to Q - F, which is accept state set of machine M'.

Assume w=w1w2w3 ... wn is rejeceted by M, and its state sequences is q0q1 ... qn, where q0 =s and qn not belongs to F. w will be accepted by M' because qn belongs to Q - F , and q0 = s, and for each qi-1 and qi, the transition function f(qi-1, wi) = qi exists.

As we can construct such a DFA M' to accept complement of a DFA, so the DFA is closed under complement.  

2. closed under star, the proof same as the proof regular language closure

3. closed under concatenation, the proof same as the proof of regular language closure under concatennation

4. closed under intersection, proof by converting the intersection to union.

5. close under difference, proof by converting the difference to union

Anyway, all the operations of DFA is closed. This is really a very good property.

### NFA

NFA, non-deterministic finite automaton, compared with deterministic, which is non-deterministic. 

it means, for each state and a input symbol, it can go to multiple next states parallelly. This computational model is more powerful! The first powerfulness lies in it allowing to guess the input. Actually nondeterminsim is a generalization of determinism.

#### definition
The definition is very similar to DFA. What the same is the definition of input symbols, start state, accept state, what the different is the definition of transition function.

The transition function is f: (q, s): A,  where A is subset of Q. 

#### equivalent to DFA

It is surprising that NFA is equivalent to DFA because  we expect that NFA is more powerful than DFA.

The proof of this step can be enlightened from just read NFA by the way of reading DFA. 

If we read NFA step by step, for the current state, we can go to multiple next states, so we can see multiple next states set as a whole single state.  And if such a set state contains final state, it should be a final state in DFA too. 

So this proof is very beautiful by the view of reading NFA as a way of reading DFA.

As for epsilon, for the current state set, for each state qi in the set, find all the states Qi that is reachable to qi by epsilon , and union such Qi to S



### Regular expression

Regular expresion is widely used in programming for searching. And it is surprising that re is equivalent to DFA and NFA. Based on this fact, we can convert re to DFA to bulild a efficient algorithm to search.

#### Definition

The definition of regular expression is very simple and inductive. Let make me feel the powerfulness of inductive definition. When we want to define something infinitive, we may use inductive definition. 

1. if a is in symbol input set, a is regular; epsilon is regular expression; empty set is re

2. If R1 and R2 is re, R1 union R2 is re; R1 concatnenation R2 is re; star of R1 is re.

#### Equivalence

The proof of equivalence has two directions, one is if re,  NFA or DFA exists; if DFA or NFA, re exists

It is very simple to prove the first direction by construction. The proof process is very similar to prove the closure of regular language. We construct union of R1 and R2 by using epsilon, and the same for concatenation and star operation.


The idea of converting NFA to re is based on the decrease and conquer. Firstly, we generate the generalized nfa, that is GNFA.  GNFA only has a start state without incoming transition, and a final state without outcoming transition. 

So adding a new start state of GNFA , which connects to the start state in the NFA. also the same for creationo of a new accept state. 

And then another difference is the transition fucntion, f(qi,qi+1) -> R, where R is a regular expression. 


After creating the GNFA, we can consider the algorithm to convert the NFA to re right now. 

we use rip it out algorithm, randomly select a state to rip out, called q_rip.

Consider the transition  qi->q_rip->qj, if we rip the q_rip out, we need to connect the qi and qj directly, so we can update the transition re from qi to qj. Ler r1r2 * r3 be the re going from qi to q_rip and qj,  let r0 be the re directly connecting qi to qj. so we can get a new re from qi to qj by updating  r0 | r1r2 * r3. 

We can repeat the above actions until only the start state and the accept state left. 

##### proof of correctness of ripping it out algorithm.

the proof is very simple,  just use induction to proof it. 

This algorithm is very beautiful because it only consider the simplest compenents , and then based on the component, use decrease and conquer technique to solve the problem, which is really very beautiful.


#### pumpming lemma of DFA

So,  some languages can be expressed by regular languages, but some languages can not be expressed by DFA or NFA, so what is the limitation of DFA and NFA. Maybe we can find the common property of the DFA or NFA, so we can find thoes languages, which is not regular language.

##### Pumping lemma

But what is pumping lemma? We can find the fact that the number of states in DFA is finite, let p be the number of states in DFA, so if a word, which belongs the DFA, with the length at least p, it means there is a repeated patterns of states in DFA, so we can use  xyz to express the word w, and y is the repetitive part, where |xy| <= p and |y| >0 , and xy^iz belongs to the DFA too.

So we can make full use of this property to prove some language is not regular. 

###### Proof of pumping lemma . 

Let L be a regular language, let w1w2...wn be the word belonging to L, let p be the number of states in DFA, and n>=p. Let q1q2 ... q_p q_(p+1)... q_n q _ (n+1)

So there are at least p+1 states in each word, so there exists at least two same states, so let qi and qj be the same states, where i < j.  so each s can be divided into three pieces, let x be the q1q2 .. qi-1, let y be the qi .. qj, let z be the qj+1 ... q _ (n+1)

It can be very easily proved that |xy| <= p, |y| > 0, and xy^iz is also belonging to L. 



### computability of DFA

everything about DFA is decidable, which means there is always a algorithm to recognize langauge about DFA.

#### {(DFA, w) | DFA accepts w}

This proof is very simple, create a TM, run w on DFA, keep track of DFA states, if DFA stops at accept state, accept; otherwise, reject.

#### {DFA | DFA is empty set}

Actually, DFA is a special graph, this can be done by useing DFS. Start from the start state, expand to the next states by finding any unmarked state which a transition coming from the current state. 


#### {D1, D2| D1 is DFA, D2 is DFA, D1 equals to D2}

This problem can be simply converted to judge whether DFA is an empty set.

#### {D | D is DFA, accepts at least 100  words}

Two conditions. The first condition is the DFA is finite, so we can count all the language , so we can directly count the number of words in DFA. 

The second condition is the DFA is infinitve, so we just need to find the DFA is infinitive, but how to find the DFA is infinitive. 

Detect the cycle, and then the reachable state is acceptable to the cycle. 

#### {D | D is a DFA, any accepts at most 100 words or accepts exactly 100 words}
This proof is very similar to the above. 







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



### NFA

NFA, non-deterministic finite automaton, compared with deterministic, which is non-deterministic. 

it means, for each state and a input symbol, it can go to multiple next states parallelly. This computational model is more powerful! The first powerfulness lies in it allowing to guess the input. Actually nondeterminsim is a generalization of determinism.


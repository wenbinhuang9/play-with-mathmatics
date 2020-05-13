Turing Machine is more powerful than DFA or PDA because the TM has unlimited memory and can randomly access the memory. 

### The definition of TM
-s0, a start state
-Q, set of states
-qaccept, an accept state
-qreject, an reject state
-S, an input symbols
-T, symbols on tape
-F, trnastition function, f(q1, s1, op) -> (q2, s2), where op is element of {L, R}, and q1, q2 is element of states, and s1, s2 is the tape symbols. 

### multiple tape TM
There is another variant of TM, that is multiple tapes TM.

multiple tapes is easier to write than TM because it allows us to make full use of multiple tapes, and 
multiple tapes help reduce time complexity.

For example, a^nb^n, we can use three tapes, and copy a to second tape, and copy b to third tape, then run the second and the third tape synchronizationly. 

Multiple tape TM is equivalent to the TM. We can just store the symbols in multiple tapes into one tape by using seperator 

### non-deterministic TM

Another variant of TM is powerful in the guessing, especially it is useful in  the language of {ww}. It just guesses.

non-deterministic TM is equivalent to TM.  It can be simulated by multiple tapes TM. The first tape store the input string, second tape used to simulation, and third tape used to keep track of the position of current NTM.


#### description of TM
- we can write the TM strictly based on the definition, but this is a very low level implementation, just like machine code
- we can also use English prose to descripe the implementation of English.
- According to the Church Turing machine, high level intuitive informal notation is equivalent to low level TM defintion, so we can use high level language to descripe the TM.

### decidable

The definition of decidable is nothing more than we can find a algorithm for some problem. 

It means no matter for what kind of input is, the TM always terminates


### acceptable

The defintion of acceptable is that if we can find a TM to accept some languages, it is acceptable. But for the input not belonging to the language, the TM may loop.

### the first undecidable question

{<TM, w> | given TM, TM accept w} this problem is undecidable. But how to prove? 

This proof is very beautiful ,it uses the diagonalization to prove.

Assume N be the natural number, and R be the real number, we can't find a one to one mapping from N to R. This proof can be done by the diagonalization.

### reductibility
Reductibility is very powerful for us to find what kind of problem is undecidable. 

For other unsolvable problems proof , we can use reducibility. Why reducibility is so powerful? 

We already know {<M, w>| M is TM and M accepts  } is undecidable in TM, for other kinds of undecidable problem, we can reduce accepting problem to that unsolvable, which means the unsolvable is also more hard than the accepting problem, let's see some classical unsolvable problems.

1. {M | M is empty set}
How we reduce this problem? We build the TM M' and w' is the input of M'.

- Run M on w
- if M accepts w, let M' go to accept state (should be everythin)
- if M rejects w, let M' go to reject state  (should be empty set)
- if M loops on w, M' loops too.

If M acepts w, which means L(M') is everything

If M rejects or loops on w, which means L(M') is empty set. 

So when L(M') is everythin, answers M accepting w. So no of empty set  answers yes of . ...

When L(M') is empty set, answers M rejecting or loops on w. yes of empty set answers no of  ... 

2. {M | M is everything}

This part is very simiar to the proof the M is empty set.

3. {M | M accepts exactly CSUEB}

Let M' go to accept state only when w' is CUSEB??? 

4. {M | M accepts at least 3 strings}

Let M' go to accept state when M accepts w.

5. {M | M accepts exactly 2 strings}

Let M' go to accept state when w' is either a or b. 


6. {<M, w> | M is a TM, M halts on w}
Let D is such a TM simulator for the above language.

Build a TM M', when M accepts w or rejects w, accept or reject it. Otherwise, run <M, w> on D, if M halts on w, reject; otherwise reject too. 








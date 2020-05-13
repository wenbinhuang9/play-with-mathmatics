## what is probability

The probability exists in our life. For example, if we cast the conins, it has 0.5 prability to be the positive. So before defining the probability, we should have experiment. A experiment has a different outcomes, so we call all the possible outcomes of an experiment is sample space. A sample space is nothing more than a set. 

From the sample space, we can define the event, event is subset of sample space, so event is nothing more than a set. 

So right now we can define the probability of a event, let U be the sample space.

1. P(E) = |E|/|U|
2. 0 <= P(E) <=1
3. P(E1) + P(E2) .. P(Ek) = 1, where Ei, Ej are mutually exclusive. 


So the above is the definition of probability. It does not illustrate what is probability, it just define the property of probability.

But what does probability mean , I think probability means the uncertainty. The uncertainty of the experiment. So where is the uncertainty coming from? Some uncertainty is naturally existing, but some uncertainty coming from the noise or bias. FOr example, if we want to compute the area of the house, the way to do that is to measure the width and the hegiht. But each time, the area is different, so there is the bias of area or we can also call noise of the measurement, this noise can come from the measurement tool, or coming from the measurement people. 

## other properties of probability

P(E1 + E2) = P(E1) + P(E2) - P(E1E2). This can be easily proved by using set theorem.

P(E1 + E2 + E3) = P(E1) + P(E2) + P(E3) - P(E1E2) - P(E2E3) - P(E1E3) + P(E1E2E3). This can also be proved by using set theorem.

## Independent definition 

P(E1E2) = P(E1)P(E2), we call E1 and E2 are independent. 

But how we interpret the independent here? 

## Conditional probability

Actually, conditional probability can be very well used to express the probabilistic reasoning.

P(X|Y), we can interpret this to be that if Y observed, what is the probability of X, if we know the fact Y, what is the probability of X, or if we know the evidence of Y, what is the probability of Y.

So conditional probability is widely used in the life.


Here is the defintion of conditional probablility.

P(X | Y) = P(XY)/P(Y)

If X and Y are independent we can get P(X|Y) = P(X), right now we can interpret what is independent. Even though we observe Y, P(X) is still unchanged. So the information of Y we get can not influence the P(X), so X and Y is independent. 

Actually, the definition of conditional probability is very interesting.

We can conlude many useful fomurla from it.

We can get P(XY) = P(Y)P(X|Y)

Further, we can get P(X1X2X3) = P(X1|X2X3)P(X2X3) = P(X1|X2X3)P(X2|X3)P(X3), this is a chaining rule. 

More generally, we can get P(X1X2..XK)= P(X1|X2 ...XK)P(X2|X3 .. Xk) ... P(Xk)




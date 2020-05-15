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

P(X|Y), we can interpret this to be that if Y observed, what is the probability of X, if we know the fact Y, what is the probability of X, or if we know the evidence of Y, what is the probability of X.


So conditional probability is widely used in the life, it can be used to reason.  Actually, when we observe y, we can make a decision about X by getting the distribution of P(X|y). 

Here is the defintion of conditional probablility.

P(X | Y) = P(XY)/P(Y)

If X and Y are independent we can get P(X|Y) = P(X), right now we can interpret what is independent. Even though we observe Y, P(X) is still unchanged. So the information of Y we get can not influence the P(X), so X and Y is independent.  We can also get insight about the independent from the perspective of division.

If we let k =  P(X|y)/P(X), if k is closed to 1, which means X, Y is closed to independent. if k is going to a very big number , which means X and Y is related, in other words, the happenning of Y will lead to the happening of X.If k is closed to 0, which means the happening Y leads to the disperance of X. 
   

Actually, the definition of conditional probability is very interesting.

We can conlude many useful fomurla from it.

We can get P(XY) = P(Y)P(X|Y)

Further, we can get P(X1X2X3) = P(X1|X2X3)P(X2X3) = P(X1|X2X3)P(X2|X3)P(X3), this is a chaining rule. 

More generally, we can get P(X1X2..XK)= P(X1|X2 ...XK)P(X2|X3 .. Xk) ... P(Xk)


If Xi and Xj is mutually independent, then we can get

P(X1X2X3 .. Xk) = P(X1) P(X2) ... P(Xk)

P(x1) = P(x1y1) + P(x1y2) + ... + P(x1yk) = P(y1)P(x1|y1) + P(y2)P(x1|y2) ... P(yk) P(x1|yk)

Then , we can also get the famous baysian formula.

P(X|Y) = P(XY)/ P(Y)

P(Y|X) = P(YX)/ P(X)

As P(XY) = P(YX)

so we get P(X|Y) = P(Y|X) P(X) / P(Y)

Then P(X|Y) = (P(Y|X)/P(Y)) P(X)

But how we interpret this formula. Firstly, We just consider the most simple case,  we give X a distribution from our objective experience. Then, we observe the information from the Y, when we observe Y, the Y will helps to adjust the probabilty of X, with more Y observed,  we have more confidence about what X will happen. (Sounds like a very confused interpretation)






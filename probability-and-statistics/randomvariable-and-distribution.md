### What is random variable

I think the definition of random variable is used to give a number for each atomic event, so  the event can be viewed as a number, which can be used to compute for convenience, for exmaple after defining the random variable, we can define the expectation. 

Informally, the random variable is nothing more than one to one  mapping from atomic event to natural number.

Formally, it is a function  f:sample space -> natural number. 

### What is distribution

Informal description, each specific value in random variable has a probability, which is called distribution.

For discrete random  variable,  we can use probability mass function to denote distribution.

As for continuous random variable, we can use probability density function to denote distribution.


### The EXPECTATION
After introduction of random variable and distribution, we can define what is expectation.

For discrete random variable, E(X) = x1P(x1) + x2P(x2) ... xkP(xk)

For coninuous random variable, we can use calculus to express it . 

### families of distribution.

1. Binominal distribution, which is the most commmon distribution, if an experiment has only two outcomes, we usually can use binominal distribution, and the limits of binominial distribution is getting closed to normal distribution. And we can also get the Possion distribution from binominal distribution. As the how to compute the probability of yes of outcomes, we can use Law of Large Number to compute the probability. SO binominal distribution looks very simple, but actually it is very important.

2. Possion distribution,  it can be derived from the binominal distribution, so beautiful. But I still don't know the application of possion distribution

3. Normal distribution, a very powerful distribution because of Central limits theorem. And this distribution is also very common in our real life. And the therem of interval confidence and hypothesis test is also built on the normal distribution. 



### Joint distribution 

P(X, Y) is a joint distribution, what does joint distribution mean ? If we konw the joint distribution  , we also get to know the distribution of P(X), P(Y), P(X|Y), P(Y|X), which means we know everythin about X, Y and X and Y. 



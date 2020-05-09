
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

Definition1, We define the addition, let m be a natural number 

0 + m = m

Suppose we have defined m adding to n denoted by n + m,
and so we define inductively that (n++) + m = (n + m)++ 

Proof1 m + 0 = m

we can prove it by induction

when m = 0, 0 + 0 = 0 because we have defined 0 +m = m, so 0+ 0 = 0

Assume when m = k, it is true, so k + 0 = k

so (k++) + 0 = (k + 0)++ = k++, it is true.

so m + 0 = m it is true. 

Proof2  m + n++ = (m + n) ++

Prove by induction.

When m = 0, we can get 0 + n++ = n++ =  n++ + 0 = (n+0)++ = (0+n)++

Assume m + n++ = (m + n) ++ is true for induction

(m++) + (n++) = (m + n++)++ = ((m + n)++)++

As we know that m++ + n = (m+n) ++, so ((m + n)++)++ = (m++ + n) ++ 

proof done. 

Proof3 n + m = m + n

Prove by induction

When m = 0, n + 0 = 0 + n, it is true

Assume n+m = m + n is true for induction

n + m++ = (n + m) ++, m++ + n = (m + n)++

so (n + m)++ equals to (m + n)++, because (n+m)= m+n

so n+m++ = m++ + n

so n+m = m+n

Proof4 (a+b) + c = a + (b + c)

proof by induction

when c = 0, (a + b) + 0 =  a + b, a + (b + c ) = a + ( b + 0) = a + b

Assume (a + b) + c = a + (b + c ) is true for induction

(a + b) + c++ = ((a + b) + c)++

a + (b + c++) = a + (b + c)++ = (a + (b + c))++

so (a+ b) + c++ = a + (b + c++)

## What is the multiplication of natural number? 


Definition of multiplication, we denote n * m is  m multiplys to n
 
1. 0 * m = 0, m multiplys to 0 is 0

2. n++ * m = (n * m) + m , I will use nm for abbrevation of n * m

Proof1 m * 0 = 0

prove by indcution.

when m = 0, 0 * 0 = 0 

Assume m * 0  = 0 is true for induction

m++ * 0 = (m * 0) + 0 = 0 + 0 = 0


Proof2 m * n++ = (mn) + m  (some problem here)

when m = 0, 0 * n++ = 0, (mn) + m = 0 + 0 = 0

Assume m * n++ = (mn) + m is true for reduction

m++ * n++ = (m * n++) + n++ = mn + m + n++ = mn + (m + n)++ = mn + m++ + n = (m++ * n ) + m++



Proof3 mn = nm

Prove by induction.

When m = 0, 0 * n = n * 0 it is true

Assume mn = nm is true for indudction

m++ * n = mn  + n

n * m++ = nm + n

m++ * n = n * m++ , because mn = nm 

Proof4 x(y + z) = xy + xz 

when z = 0, x(y + z) = x(y + 0 ) = xy; xy + xz = xy + x0 = xy

Assume x(y + z) = xy + xz is true for induction

So x(y + z++ ) = x((y+z)++) = ((y+z)++)x = (y+z)x + x = xy + xz + x =
xy + x(z++)


Proof5 (xy)z = x(yz)

Prove by induction

When z = 0, (xy) * 0 = 0, x(yz) = x (y * 0) = x * 0 = 0

Assume (xy)z = x(yz) true for induction

(xy)z++ = (xy)z + (xy)
x(yz++) = x(yz + y) = x(yz) + xy = (xy)z + xy = (xy)z++


Proof6 if a, b are natural number, and c is positive, a < b, then ac < bc

Proof

When c = 1, ac = a0++ = a0 + a = a, bc = b, so a < b

Assume ac < bc true for induction

ac++ = ac + a,  bc++ = bc + b, ac + a < bc + b because a < b and ac < bc

Proof7 Let a, b, c be natural number such that ac = bc and c is non-zero. Then a = b.

Prove, Assume a not equal to b for sake of contraction, so at this time a is either smaller thant b or greater than b .

If a < b, we can get ac < bc, contradicing ac = bc

If a > b, we can get ac > bc, contradiciting ac = bc

if a = b is true. 


Proof7, let n be a natural number, and let q be a positive number. There exist natural number m, r such that 0<= r < q and n = mq + r.


Proof, by induction

When n = 0,  0 = mq + r, so we can find m = 0, r = 0, such that mq + r = 0q + 0 = 0

Assume n = mq + r true for induction

n++ = n + 1 = mq + r + 1 = mq + r++, there exist two conditions here,

if r++ = q, so mq + r + q = mq + q = (m++)q + 0, so we can find m++, and 0 

if r++ < q, so we can find m and r++ 

 
### What is the exponentiation of natural number 

we can recursively use multiplication to define exponentiation.

Definition of exponentiation, let m be a natural number 

we denote m to the power of 0 by m^0 = 1

we denote m to the power of natural nummber n++, m^(n++) = m^n * m (Oh, beautiful, this is a recursive definiton, powerful!!!)

Proof1, let m be a natural number, 0^n = 0 

When n = 0, 0^0 = 0

Assume 0^n = 0 true for induction

0^n++ = 0^n * n = 0 * n = 0


Proof2 m^a * m^b = m^(a + b)

When a = 0 , m^0 * m^b = m^b, m^(a+b) = m^b

m^a * m^b = m^(a + b) true for induction

(m)^(a++) * m^b = m^a * m * m^b = m^a * m^b * m = m^(a + b ) * m = m^(a + b + 1) = m^(a++ + b)

 

## What is the integer.
we can define minus, and then use minus to define integer, is this a good choice??? , or just like increment operation, we define decrement operation, is this ok too?? 

We have defined the natural number, but what is integer number? 

Definition, n is a number

1. if n is a natural number, n is an integer

2. 

think about this with more details.


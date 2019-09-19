---
title: "Tutorial 01"
date: 2019-09-19T16:04:34+10:00

categories: ["Tutorials"]
hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Question One

> **a.** Explain why each composite integer `n` has a prime factor of size at most `sqrt(n)`

_Suppose that the above is false,_  
that all the prime factors of `n` have a size strictly greater than `sqrt(n)`

Let `n = km; k,m > 1`

Then `k,m > sqrt(n)`, so `n = km > (sqrt(n))^2 = n`.  
This is a contradiction

> **b.** Explain why, for `18 <= n <= 400`, `n /= 361`, that `n` is prime iff `n` does not have 2 or 5 as a proper factor, and `gcd(n, 51051) = 1`

From **(a)** - `n` is prime if `n` has no factors less than or equal to `sqrt(n)`

Prime factors less than 20: 2, 3, 5, 7, 11, 13, 17, 19.

* Ignore (2) (5)
* `19^2 = 361` but `n /= 361` so ignore (19)
* `51051 = 51 * 1001`
  * `51 = 17 * 3`
    * Ignore (3) (17)
  * `1001 = 11 * 7 * 13`
    * Ignore (7) (11) (13)

Hence there are no factors

> **c.** Hence test `n = 323` and `n = 373`

* `323` divides by 17, so `n = 323` is not prime.  
* `373` is not divisible by the above factors, so `n = 373` is prime.

# Question Two

- Skip -

# Question Three

> **a.** What is the probability of picking a Queen from a standard pack of cards?

4/52 = 1/13

> **b.** If I have picked a face card, then what is the probability that it is a Queen?

4/12 = 1/3

> **c.** If I have picked a black card, then what is the probably that it is a Queen?

2/26 = 1/13

# Question Four

> A certain binary information channel is more likely to transmit a 0 as an error for 1
than a 1 as an error for 0. The probability that a 1 is received in error is 0.1 (that is,
P (1 received | 0 sent) = 0.1) and the probability that a 0 is received in error is 0.2. Write
down the conditional probabilities for all four possible situations.

`P(1s) = 0.5`  
`P(0s) = 0.5`  

`P(1r | 1s) = 0.8`  
`P(1r | 0s) = 0.1`  
`P(0r | 1s) = 0.2`  
`P(0r | 0s) = 0.9`  

> If 1s and 0s are sent with equal probability, find the probability of receiving a zero.

`P(0r) = P(0r|0s)*P(0s) + P(0r|1s)*P(1s)`  
`= 0.9*0.5 + 0.2*0.5`  
`= 0.55 = 55%`

> What is the probability that a zero was sent, given that a zero was received?

`P(0s | 0r) = P(0s and 0r) / P(0r) = P(0r | 0s)*P(0s)/P(0r)`  
`= 0.9 * 0.5 / 0.55`  
`= 9/11 = 0.81 = 81%`

# Question Five

> The famous and much debated Monty Hall problem is as follows:  
On a game show, a contestant is presented with three identical doors, behind one of which is a major prize, the others hiding a minor prize. The contestant gets to choose one door. If the contestant picks the door hiding a minor prize, then the host, Monty Hall, opens the door showing the other prize; if the contestant picks the door with the major prize, Monty randomly picks one of the doors hiding a minor prize and opens that. The contestant then has the choice of changing to the other door or not, and wins whatever is behind the door he or she has finally settled on.

> Should the contestant change to the other door? Can you prove your
answer?

Yes - re-evaluate your choices given the options

# Question Six

> `n` bits are sent, each independently with error probability `p`.  
Let `X` be the number of errors

> **a.** Find `P(X = k)`

`= bin(n,k) p^k (1-p)^(n-k)`

> **b.** Find `P(X is even)`

`= P(X=0) + P(X=2) + ...`

> **c.** Show that the answer in **(b)** can be expressed as `(1 + (1-2p)^n) / 2`

_Hint: Let `q = 1 - p` and expand `((q+p)^n+(q-p)^n)/2)`_

# Question Seven

Taking `p = .001` and `n = 100` in Question 6, find the probability that

> **a.** there is no error

`P(X=0) = (1-p)^n = 0.9048`

> **b.** there is an undetected error when a simple parity check (even mode) is used.

`P(X is even, but not zero) = 0.0045`

<!-- # Question Eight -->


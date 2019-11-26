---
title: "Lecture 11"
date: 2019-10-25T14:00:00+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

Channel capacity $C = C(A,B) = max I(A,B)$

Max - when the differential is 0

Channel capacity of a binary symmetric channel, crossover probability $p = 1 - H(p)$

---

Shannon's Noisy Channel Coding Theorem
---



# ch5

-- Euclidean Algorithm - find the gcd


bezout's idebtity

for x,y in Z

d = gcd(a,b) = ax + by


Chinese remainder theorem
For any coprime integers p and q and any m1, m2 in Z, the congruences x === m1 mod p and x === m2 mod q have auniqe common solution modulo pq

The alement a  in Z_M is invertible (is a 'unit') if it has an inverse 1^-1 in Zm

a is invertibleo only if gcd(a,m) = 1

Um is the set of units of Zm
aka, the set where gcd == 1
  aka Um = {a in Zm : gcd(a,m) = 1}
  if (m = p) is prime then Um = {1,2,...,p-1}

Euler's phi-function: $\phi(m) = |U_m|$
if $p$ is prime, then $\phi(p) = p - 1$

if gcd(m,n) = 1 (aka if two numbers are coprime) then phi(mn) = phi(m) * phi(n)
phi(p^\alpha) = p^\alpha - p^{\alpha-1}

To find for any, factorise into their prime factors, then we can find the product (as phi(mn) = phi(m)phi(n))
\phi(m) = p_1^{\alpha_1}(1-1/p_1)


Fermat's little theorem

Let p be a prome number and a be an intefger

a^p === a mod p
a^{p-1} === 1 mod p whenever p !/ a

--

Calculate 3^125 (mod 7)
... = 5 mod 7


Euler's theorem
If a, n are positive integers with gcd(a,n = 1t hen a^{\phi(n)} === 1 mod n

Calculate 7^131 mod 12

phi(12) = 4, so 7^4 mod 12 = 1


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


# Ch 5

-- Euclidean Algorithm - find the gcd

# Bezout's Identity

for x,y in Z, $d = gcd(a,b) = ax + by$

# Chinese remainder theorem

For any co-prime integers $p$ and $q$ and any $m_1$, $m_2$ in $Z$, the congruences $x === m_1 mod p$ and $x === m_2 mod q$ have a unique common solution modulo $pq$

The element $a$ in $Z_M$ is invertible _(is a [unit](../units.md))_ if it has an inverse $a^-1$ in $Z_m$

$a$ is invertible only if $gcd(a,m) = 1$

$U_m$ is the set of units of $Z_m$  
aka, the set where $gcd == 1$
  aka $U_m = {a in Zm : gcd(a,m) = 1}$
  if $(m = p) is prime then Um = {1,2,...,p-1}$

Euler's phi-function: $\phi(m) = |U_m|$  
if $p$ is prime, then $\phi(p) = p - 1$

if $gcd(m,n) = 1$ (aka if two numbers are co-prime) then $phi(mn) = phi(m) * phi(n)$
$phi(p^\alpha) = p^\alpha - p^{\alpha-1}$

To find for any, factorise into their prime factors, then we can find the product (as $phi(mn) = phi(m)phi(n))$  
$\phi(m) = p_1^{\alpha_1}(1-1/p_1)$

# Fermat's Little Theorem

Let $p$ be a prime number and $a$ be an integer

$a^p === a mod p$  
$a^{p-1} === 1 mod p whenever p !/ a$

--

Calculate $3^125 (mod 7)$  
... = 5 mod 7

# Euler&apos;s theorem

If $a$, $n$ are positive integers with $gcd(a,n) = 1$ then $a^{\phi(n)} === 1 mod n$

Calculate $7^131 mod 12$

$phi(12) = 4$, so $7^4 mod 12 = 1$

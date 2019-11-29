---
title: "Lecture 12"
date: 2019-10-29T12:18:42+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

The order of an element a in U_m is ord_m(a) = min{i in Z+ : a^i = 1}

The exponent for which a^i === 1 mod m

---

If ord_m(g) = |U_m|, then g is a primitive element of Um
Primitive -> U_m= \<g> = {g, g^2, ..., g^{\phi(m)}

ord_m(a) | \phi(m)
A primitive element g of Up exists whenever p is prime
If g is a primitive element of Um, then g^k is also a primitive element iff gcd(k, \phi(m)) = 1

If um has a primitive element then it has \phi(\phi(m))

---

Let F be a **field**

Z_p is a field iff p is prime
-> Non-prime values of p do not have non-zero inverses

A polynomial f over F is a sum of the form
f = a_nx^n + a_{n-1}x^{n-1} + ... + a_1x + a_0

where a_e in F are the coefficients of f

if a_n = 1 then f is monic
if a_n =/= 0 then the degree of f is deg f(x) = n
the degree of the zero polynomial f=0 is -\infty
the set of all polynomials over F is denoted by F[x]

Division Algorithm for F[x]

if f,g in F[x] with g =/= 0
then f, qg  + r and deg r < deg g for unique polynomials q,r in F[x]

eg

Consider f=4x^3 + x and g = 2x + 1 where f,g in Z_5[x]
Find q,r in Z_5[x] so that f=qg + r and deg r < deg g


# Remainder theorem

if f in F[x] and c in F
then f = q(x-c) + f(c) for a unique polynomial q in F[x]

The Factor theorem for f[x]
if f in F[x] and c in F, then f(c) = 0 if an d only if (x-c)| f
\alpha in F is a root of f in F[x] if f(\a) = 0


 A polynomial f in F[x] has at most deg f roots

f in F[x] is irreducible if it has no proper factors of positive degree

a greatest common divisor of f,g in F[x] is a common divisor of f and g that is divided by every other common divisor  
the monic greatest common divisor of f and g is denoted by gcd(f,g)

# Euclidean Algorithm for $F[x]$

Find $gcd(f,g)$ for $f=x^4+2x^3+2x^2$ and $g=x^2+2x+1$ in $Z_3[x]$

f = ... * g + ...

Remainder mod r -> negative becomes positive

---

Let $m = x^n + a_ .... + a0$ be a monic polynomial in $Z_p[x]$

The multiples of $m$ are denoted as ${am : a in Z_p[x]}$  
the set of polynomials $Z_p[x]$ modulo $m$ is denoted $Z_p[x]$

# Lemma

Z_p[x] / {b_n-1 x^n-1 + ... + b0 : b_i in Z_p}

Remainders of degrees up to $m-1$
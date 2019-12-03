---
title: "Error Correction and Detection"
date: 2019-09-27T14:09:41+10:00
description: "And sphere packing"
categories: ["Lectures"]
hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

C = {`Hello`, `Help!`}

Sending `Hello`, receiving `Hell!`

d(`Hello`, `Hell!`) = 1  
d(`Help!`, `Hell!`) = 1

---

# Error Probability

The probability of there being $k$ errors in an message of $n$ bits is.

$P(X=k) = nCk p^k (1-p)^{n-k}$

Depending on the error checking strategy, we might only count some $k$.

* Pure-detection: 1..n-1
* Even parity, 2, 4, 6, 8, ...
* Odd parity: 1, 3, 5, 7, ...

# Strategies

## Minimum distance decoding

> Snap to the codeword with the smallest change

Example: Given a received word y, decode to closest codeword X.

|   C = {`Hello`, `Help!`}    |
| :-------------------------: |
|   d(`Hello`, `Halp!`) = 3   |
| d(`Help!`, `Halp!`) = **1** |

So assume to be `Help!`

### The odd case - single codeword that the closest

- if $minimum distance = 2t + 1$, then $C$ is a $t$-error correcting code

### The even case - when there are equidistant codewords

- If $minimum distance = 2t + 2$, then $C$ is a $t$-error correcting, and $t + 1$-error detecting code.

## Standard Strategy

> If received word $y$ is distance at most $t$ from a codeword $x$, then decode $y$ to $x$, otherwise flag an error

> Snap up to a distance at most $t$ away

$d = 5$  
$t = 2$

## Pure error detection

> Give up completely.

## SUMMARY

- If $e+f=d-1$ and $f>=e$, then there is a strategy which is $e$-error correcting and $f$-error detecting
- If $d = 2t + 1$, then $C$ is $t$ error correcting
- If $d = 2t + 2$, then $C$ is $t$ error correcting and $t+1$ error detecting

---

Let $c \in Z_2^n$ be an $n$-bit word.

The sphere of radius $r$ around $c$

\$S_r (C) = {x \in Z_2^n : d(x,c) <= r}

The volume of this sphere is its size |S_r(c)|

Example

| For c = 1100 s(1) |
| :---------------: |
|       1100        |
|       1101        |
|       1110        |
|       1000        |
|       0100        |

| For c = 1100 s(2)  |
| :----------------: |
|        1100        |
|        1101        |
|        1110        |
|        1000        |
|        0100        |
| :----------------: |
|        1111        |
|        1001        |
|        0101        |
|        1010        |
|        0110        |
|        0000        |

---

# Theorem

$|S_r (c) | = 1 + (n;1) + (n;2) + ... + (n;r)$

## Example

Consider the code $C = {000, 111}$

$S_1(000) = {000, 001, 010, 100}$  
$S_1(111) = {111, 110, 101, 011}$

---

If the spheres of radius $r$ around each codeword $x$ do not overlap, then they form a **sphere packing**.

- Small enough as to not overlap
- Big enough to correct things

## Sphere-Packing Condition Theorem (binary case)

A $t$-error correcting binary code $C$ of length $n$ has minimum distance $d = 2t + 1$ or $2t + 2$, and

$|C| \Sum_(i=0)^t (n;i) <= 2^n$

-- Work out $d$ first, then work out $t$

A binary code is **perfect** if it achieves equality (covers everything) ( ... = 2^n)

### Example

A $1$-error correcting binary code $C$ must satisfy $|C|(1+n)<=2^n$

\$|C| (nC0 + nC1)\$

---

A linear code C is a vector space over some field $F$.

It is the null-space or kernel $C = {x \in F^n : Hx^T = 0}$
of an $m \times n$ parity check matrix $H$ with $m = rank(H)$

- $dim C = k = n-m$ (rank nullity theorem)
- If C is binary, then $|C| = 2^k$
- C is systematic
- If H is in REF, leading columns - check bits, non-leading - information

---

If C is a linear code with parity check matrix H, then

- w(C) = d(C)
- d(C) = min {r:H has r linearly dependant columns}
  <!--
  If d(C)=1 - then it means that one column is the same as another
  if d(C)=2 then there is a column that is all zeros -->

---

The parity check matrix of a Hamming-type code C with m>=2 and n>=3 has no repeated column, but columns 1,2,3 are linearly independent.

---

Suppose that C is a binary linear code with d(C) = 2t+1 or d(C)=2t+2.
Let x\inC and suppose that X~->y with u<=t errors.
Then y=x+e_i_1 + ... + e_i_u for u stadard unit vectors e_i_j

$S(y) = Hy^T = H(x^T + H_e_i^^T + ... + H_E_i_u^^T)$

$= He_i_1^^T + ... + He_i_u^^T$

We can see that Hy^T is the sum of u columns of H.

Suppose that Hy^T is also another columns of u' <= t columns He_j_l of H

Then He_i_1^^T + ... + H_e_i_u^^T + He_j_1^^T + ... + He_j_u'^^T = Hy^T + Hy^T = 0

2t lots of columns, but that is less than d

So only one unique sum.

The received word y = 11001 has a single error.

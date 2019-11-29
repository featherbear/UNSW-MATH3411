---
title: "Generator Matrices"
date: 2019-10-01T12:08:30+10:00

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

A linear code $C$ is a vector space over some field $F$.

Usually $F$ is finite.

Equivalently, a linear code is the null-space or kernel $C = {x \in F^n : Hx^T = 0}$

For a $n$ column parity check matrix.  
$m$ is the number of leading columns - these will be the check bits (by choice)  
$k$ = $n - m$ is the number of non-leading columns - the information bits (by choice)

---

Given a code, finding basis: Gram-Schmidtt

* G has size $k * n$  
* H has size $m * n$  
* $k + m = n$

Can apply row operations on a generator / parity check matrix and it will still be a generator / parity check matrix

The RREF of the generator matrix G for C is also a generator matrix for C

Example, G = [0;1|1;1|1;0|1;1] spans the linear code C = {0000, 0110, 1101, 1011}

G' = [1;0|0;1|1;1|1;0]

--

Standard form of a parity check matrix  
$H = (I_m | B)$ where B is an $m * k$ matrix

Standard form of a generator matrix  
$G = (D|I_k)$ where D is a $k * m$ matrix

## `I_...` is the identity matrix

## Finding a generator matrix

For a linear code $C$ of dimension $k$ and length $n = k + m$

> $G = (B|I_k)$ is a generator matrix for $C$ iff $H = (I_m | -B^T)$ is a parity check matrix for $C$

- This can work the other way around too, to find a parity check matrix.

### Example

A linear code C over $Z_3$ has generator matrix

```
1 2 0 1 0
2 2 0 0 1
```

We can see the identity matrix in the last two columns.

The first three columns can then be regarded as $B$

$-B^T$ is then

```
-1  -2
-2  -2
0    0
```

So then,

$H = (I_m | -B^T)$

which is

```
1 0 0 1 0
0 1 0 0 0
0 0 1 0 0
```

(remember, 2 = -2 = 0, -1 = 1 in binary)

---

Linear codes are equivalent if C' is obtained by permuting the codeword entries of C by a fixed permutation

$C' = CP = {xP : x in C}$ for some permutation matrix $P$

$G' = GP$ and $H' = HP$

For example,

```
1 0 1 0 1 0 1
0 1 1 0 0 1 1
0 0 0 1 1 1 1

switch 3 and 4

```

```
1 0 0 1 1 0 1
0 1 0 1 0 1 1
0 0 1 0 1 1 1
```

---

# Code Operations

## Puncturing

## Shortening

## Extending

The extension of a linear code, is adding an extra bit such that the sum of a code is zero

The extension $\hat{C}$ is a linear code with minimum distance $d(C)$ or d(C) + 1

---

Furthermore, if H is a parity check matrix for C, then,

H hat

```
1 1 . . . 1
0
.
.     H
.
0
```

Hhat x^T = 0

---

??

--

# Radix $r$ Hamming codes

Let $r$ be a prime number and $m\ge1$ for some integer

Write the numbers $1,...,r^m - 1$ in base $r$, as length $m$ column vectors

Of each set of $r-1$ parallel columns, delete all whose first nonzero entry is not 1

This gives the radix $r$ Hamming code of length \$n= (r^m-1)/(r-1)

---

?
?
?

---

# Error Correcitng in Radix $r$

Let $x\inC$ and suppose that $x->y$ with $s$ errors

Then $y = x + a_1 e_i_1 + ... + a_s e_i_s$ where $a_i$ are non-zero scalars

The syndrome of \$y\$ is \$S(y) = Hy^T = \$H(x^T + a\*1 e\*(i\*1)^T) + ... + a_s e\*(i_s)^T)\$

= Hx^T + a*1 H e*(i*1)^T + ... + a_s H e*(i_s)^T

= 0 + a*1 H e*(i*1)^T + ... + a_s H e*(i_s)^T

= a*1 H e*(i*1)^T + ... + a_s H e*(i_s)^T

$Hy^T$ is a linear combination of s columns

If $2s < d(C)$ then $S(y)$ is a unique linear combination of columns of H

--
example
--

---

Correcting radix:

Find the column that is a scalar multiple (a) of the result,
then correct that column, SUBTRACTING a

(Don't evaluate the result to a number)

---

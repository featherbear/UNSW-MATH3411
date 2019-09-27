---
title: "Lecture 03"
date: 2019-09-24T12:17:21+10:00
hiddenFromHomePage: false
postMetaInFooter: false
categories: ["Lectures"]

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Binary Hamming error-correction

A code $C$ that

- is binary with the code alphabet ${0, 1}$
- has fixed length $n$ codewords $x = x_1 ... x_n$
- is **only single-error correcting**
- provides user-friendly error-correcting
- uses $m$ independent linear parity checks

## Encoding Scheme

The encoding scheme is arbitrary, but it is common for the 'check bits' to be the leading columns, and the 'information bits' to be the non-leading columns.

## Correction Handling

$\sum_(j=1->n) a_ij x_j === 0 (mod 2) where i = 1,...,m and a_ij \in {0,1}$

$Hx^T = 0$ (in $Z_2$)

Where $H$ is the $m x n$ parity check matrix with entries $a_ij$

Let $C$ be the null space of $H$  
(set of all vectors where $Hx^T = 0$)

Define the syndrome $S(y) = Hy^T$

- $S(x) = 0$ iff $x \in C$
- $S(y)$ tells us when $y$ has an error

Let $x$ be a codeword of $C = {x \in Z_2^n : Hx^T = 0 }$.
Consider a word $y$ with a single error (x ~- y) in position $i$

Then $y^T = x^T = e_i$
So $S(y) = Hy^T = H(x^T + e_i) = Hx_T + He_i = 0 + H e_i = H e_i$

<!-- Now, H e_i  is the ith column of H so we can make error-correcting easy by defining the ith column of H to be  -->

The binary Hamming-type code for n = 7, m = 3 has parity check matrix

H =

```
1 2 3 4 5 6 7
-------------
1 0 1 0 1 1 1
0 1 1 0 0 1 1
0 0 0 1 1 0 1
```

We call this parity check matrix for the binary $Hamming(7,4)$ code ( 4 = 7 - 3 ...)

$H * x^T = 0$

The word $y = 00111$ has a single error

To find this error we calculate the syndrome $S(y)$

S(y) = Hy^T = ( : | : | : ) ( : ) = (0;1;0)
This corresponds to the binary number 010, namely 2

We therefore correct bit number 2 and get the codeword 01111

- Decoding: get rid of the check bits
  extract the sequence of parametric variable values

eg

```
1 0 1 0 1
0 1 1 0 0
0 0 0 1 1
```

w = 01, x3 = 0, x5 = 1

(We set the non-leading columns to the values of the word)

Then multiplying the matrix by (x1;x2;x3;x4;x5)

$x_1 = 1$  
$x_2 = 0$  
$x_3 = 0$  
$x_4 = 1$  
$x_5 = 1$

So 10011

Remove the non-zero entries

Taking out the check bits; we get 01

# Encoding

Which bits will be used?

---

# Binary Hamming (n,k) codes

- Binary
- Block coces with codeword length $n$
- Systematic
- $k$ information bits
- $m = n - k$ check bits (in positions 1,2,4,...2^(m-1))
- $2^k$ codewords
- $2^m = n + 1$

For the Hamming(7,4) code.

```
1 0 1 0 1 0 1
0 1 1 0 0 1 1
0 0 0 1 1 1 1
```

a) Encode 1001
w = 1001

Leading columns are the check bits
So look at the information bits x3 x5 x6 x7

```
1 0 1 0 1 0 1
0 1 1 0 0 1 1 x  x1;x2;1;x4;0;0;1
0 0 0 1 1 1 1
```

x_1 + 1 + 1 = 0  
x_2 + 1 + 1 = 0  
x_4 + 1 = 0

x1 = 0
x2 = 0
x4 = 1

so

=== 0;0;1;1;0;0;1

b) Correct and decode 0110001

y = 0110001

```
              1 0 1 0 1 0 1
S(y) = Hy^T = 0 1 1 0 0 1 1 x 0;1;1;1;0;0;0;1
              0 0 0 1 1 1 1
```

= (2;3;1) -> (0;1;1)

011 is 6th column!

So there is an error on the 6th columns

Fixing... we get 0110011  
Now decoding, remove the check bits x1 x2 x4

So 1011

---

Hamming weight - $w(x) = | {i : x_i \ne 0} |$  
Minimum weight - $w(\) = min {w(x) : x \in C, x \ne 0} $  
Weight - 'sum' / number of 1 bits

---

- The 8-bit ASCII has minimum weight $w = 2$
- Hamming has minimum weight 3

Hamming distance from X to Y, number of bits that are different between X and Y
minimum distance, smallest not zero
max, largest

// d(&middot;, &middot;) is a **metric** on $Z_2^n$

d(x,y)>=0
d(x,y) = 0 iff x=y
d(x,y) = d(y,x)
d(x,z) <= d(x,y) + d(y,z)

//

w(x) = d(x, 0)
d(x,y) = w(x-y) [if x,y are over an Abelian group]

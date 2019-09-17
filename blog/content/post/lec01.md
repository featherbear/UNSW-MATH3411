---
title: "Lecture 01"
description: "Revision"
date: 2019-09-17T12:20:57+10:00

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

# Digital Data Transmission (as Maths)

- **Source Alphabet** - _S_ = {s1, s1, ..., sq} of q symbols
- **Code Alphabet** _A_, consisting of _r_ symbols
  - The **radix** _r_ is the number of symbols in the code alphabet
- Probabilities p_i = P(S_i)
- A code that encodes each symbol s_i by a codeword (string of code symbols)
- Codewords can be seen as **vectors**. 1001101 corresponds to (1,0,0,1,1,0,1) \in \doubleZ_2^7

# Modulo Arithmetic

If _a_, _b_ are integers, and _b > 0_ then, _a = qb + r_  
for unique integers _q_, _r_, with r \in {0,1,...,b-1}

Here q is the quotient and r is the remainder, we define r = a mod b

**Therefore...**

Integers _a_ and _b_ are congruent when modulo with m, and can be denoted by a === b (mod m).
(a mod m) = (b mod m)

## Examples

- 3+4 === 7 === 2 mod 5)
- 3-4 === -1 === 4 mod 5)
- 3x4 === 12 === 2 (mod 5)
- 3x2 === 6 === 1 (mod 5)
- 3^-1 === 2 (mod 5)

## The mod n set

For binary numbers, we have the set Z2 = {0,1} modulo 2.

- 1 + 1 = 0 in mod 2

### Examples

- in Z_8
  - 3 + 5 = 1
  - 3 - 5 = 5
  - 3 x 5 = 1
  - 3^-1 = 5

# Probability

## Bayes' Rule

![](https://miro.medium.com/max/1468/1*LB-G6WBuswEfpg20FMighA.png)

<details><summary>More</summary>
<img src="https://images.squarespace-cdn.com/content/v1/54e50c15e4b058fc6806d068/1453490707056-2PF9LAZEDO3GBJYWYU00/ke17ZwdGBToddI8pDm48kG7ejt4vIFQNL8gw02H4tglZw-zPPgdn4jUwVcJE1ZvWQUxwkmyExglNqGp0IvTJZamWLI2zvYWH8K3-s_4yszcp2ryTI0HqTOaaUohrI8PIL5qfmBPuCWOsBolAJrR_0bcFLhcJww53qBDxtFJXu78KMshLAGzx4R3EDFOm1kBS/image-asset.jpeg?format=750w"/></details>

# Linear Algebra

- A **linear combination** is a combination of vectors
- Vectors are **linearly dependent** if there is a vector can be expressed as a linear combination of the other vectors
- Else, they are **linearly independent** (only way to form 0 is the zero vector)
- The **span** is a set of all linear combinations
- The **basis** is a collection of linearly independent vectors that span a set of vectors

---

# Codes

## Morse Code

Morse code is a ternary code (radix of 3).

It has the symbols:

| Symbol   | Meaning |
| -------- | ------- |
| &middot; | dot     |
| &hyphen; | dash    |
| &#x23b5; | pause   |

## ASCII

![](https://www.sciencebuddies.org/references/ascii-table.png)

### Parity / check bit

(for error detection)

The first bit of an 8 bit ASCII character can be used to partially detect errors.

Even operation - The sum of the bits should be even.  
Odd operation - The sum of the bits should be odd.

#### Example

Suppose that we transmit 7-bit ASCII at 7x10^6 bits/s (aka 10^6 bits per second), and the probability of a given bit being in error is p = 10^-6, independently of the other bit errors

_a) What is the probability of an incorrectly transmitted word?_

P(errors) = 1 - P(No errors) = 1-(1-p)^7 = 7 x 10^-6

_b) If a parity check were to be used, what is the new probability of an incorrectly transmitted word?_

1/8 x (7 x 10^6) x (2.8 x 10^11) ~= 2.5 x 10^-5

Only one error every 11 hours!!!

_...huh?_

## ISBN

ISBN: **I**nternational **S**tandard **B**ook **N**umber

### 10-digit ISBN

The first 9 bits correspond to the country group, publisher and title. The last bit is used as a checkbit with a character from /[0-9X]/

`(sum i * xi from 1 to 10) = 0`

separate x_10
10 mod 11 === -1 mod 11

`x_10 = (sum i * xi from 1 to 9) % 11`

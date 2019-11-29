---
title: "Compression"
date: 2019-10-04T14:03:38+10:00

description: "Kraft-McMillan"
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

# Chapter Three - Compression Coding

- Variable length codes
- Assume there is no channel noise - source coding

- Define $S$ with symbols $s_1, ..., s_q$ with probabilities $p_1, ..., p_q$.
- Define code $C$ with codewords $c_1, ..., c_q$ of lengths $l_1, ..., l_q$ and radix $r$

* A code $C$ is uniquely decodable (UD) if it can always be decoded unambiguously
* A code is instantaneous if no (entire) codeword is the prefix of another (might need to read from right to left)

Codewords can have different lengths, where the more frequent codewords may have shorter lengths than that of rarer codes

**Just because a codeword is unique decodable and user-friendly, doesn't mean that it will be good for compressing**

# Decision Trees

Decision trees can represent instantaneous codes,

**Example**  
c1 = 0  
c2 = 10  
c3 = 110  
c4 = 1110  
c5 = 11110  
c6 = 11111

- 0 -> c1
- 1
  - 0 -> c2
  - 1
    - 0 -> c3
    - 1
      - 0 -> c4
      - 1
        - 0 -> c5
        - 1 -> c6

**Example**

c1 = 00  
c2 = 01  
c3 = 10  
c4 = 11

- 0
  - 0 -> c1
  - 1 -> c2
- 1
  - 0 -> c3
  - 1 -> c4

## Improving compression

- When looking at a decision tree, remove the possibly redundant data.

* Branches are numbered top-down
* Any radix $r$ is allowed
* Two codes are equivalent if their decision trees are isomorphic (same shape)
* By shuffling source symbols we may assume that l_1 <= l_2 <= ... <= l_q
  - Codewords of the smallest length at the top

## Kraft-McMillan Theorem

1. There is a radix $r$ UD-code with codeword lengths $l1 \le l_2 \le ... \le l_q$

2. There is a radix $r$ I-code with codeword lengths $l1 \le l_2 \le ... \le l_q$

3. $K = \sum_(i-1)^q (1/r)^(l_i) <= 1$

---

> Is there a radix $2$ UD-code with codeword lengths 1, 2, 2, 3?

$(1/2)^1 + (1/2)^2 + (1/2)^2 + (1/2)^3 = 9/8 \nle 1$

Hence, by the Kraft-McMillan theorem, there is no radix 2 UD code

> Is there a radix $3$ I-code with codeword lengths 1,2,2,2,2,3?

- 0 (1)
- 1
  - 0 (2)
  - 1 (2)
  - 2 (2)
- 2
  - 0 (2)
  - 1
    - 0 (3)

Through the theorem, $22/27 \le 1$

# Proof

## 2 => 1 is trivial

## 1 => 3

Suppose that a radix $r$ UD-code has codeword lengths $l_1 \e ... \le l_q$.

Raise $K$ to $n$ -> $K^n$  
= \sum\_(j=1)^\infty N_j / r^j

- $N_j$ is the number of codewords whose factors add to $j$
- $r^j$

Since the codes are uniquely decodable, each message can only be written in one way, so $N_j \le r^j$

```
So, \$K^n = \sum\_(j=1)^(nl_q) N_j / r^j$
$\sum\_(j=1)^(nl_q) N_j / r^j <= \sum\_(j=1)^(nl_q) r^j / r^j$
$= \sum\_(j=1)^(nl_q) 1 = nl_q\$
```

So $K <= 1$

## 3 => 2

Suppose $K \e 1$, then $c_i = c_i1 c_i2 ... c_il_i$ where they satisfy $\sum (j=1) -> (i-1) 1/2^(l_j)$

= c_i1/2 + c_i2 / 2^2 + ... + c_il_i / 2^l_i  
= \sum k=1 -> l_i c_i_k / 2^k

- Assume the code is not instantaneous

Then some codeword is a prefix of another, and $l_u \lt l_v$

Then, $\sum_(j=1)^(v-1) 1/2^(l_j) - \sum_(j=1)^(u-1) 1/2^(l_j) = \sum_(j=u)^(v-1) 1/2^(l_j)$

. >= 1/2^(l_u)

But $\sum_(j=1)^(v-1) 1/2^(l_j) - \sum_(j=1)^(u-1) 1/2^(l_j) = $
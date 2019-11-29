---
title: "Information Theory"
date: 2019-10-15T12:06:28+11:00

description: "Shannon-Fano Codes, Gibbs' Inequality"
hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

# Chapter Four - Information Theory

Let $I(p)$ be the amount of information given by an event of probability $p$.

* $I(p) \ge 0$ for $0 \le p \le 1$
* $I(1) = 0$
* $I$ is continuous
* $I(p_1p_2)=I(p_1) + I(p_2)$ for independent events

> $I(p) = kln(p)$ for some $k \lt 0$

* $I(p) = I_r(p) = -log_r p$ 
  * MATH3411 always uses $p=2$

## Shannon entropy of S

$H(S) = H_2(S) = \sum_{i=1}^q p_iI(p_i) = - \sum_{i=1}^q p_i log_2 p_i$

**Example - Single coin toss**  
H(S) = -1/2 log_2 1/2 + -1/2 log_2 1/2

**Example - Double coin toss, counting heads**  
p_1 = P(TT) = 1/4  
p_2 = P(HT, TH) = 2/4  
p_3 = P(HH) = 1/4  

There are 0 heads 1/4 of the time.  
There are 1 heads 1/2 of the time.  
There are 2 heads 1/4 of the time.  

H(S) = (-1/4 log_2 1/4) + (-1/2 log_2 1/2) + (-1/4 log_2 1/4) = 3/2

On average, there are 3/2 bits of information

**Example - Huffman code**  
$P = 0.3, 0.2, 0.2, 0.1, 0.1, 0.1$  
$H(S) = -\sum_{i=1}^q p_ilog_2p_i$
= 2.446

**Example - Arithmetic coding**  
$P = 0.4, 0.2, 0.2, 0.1, 0.1$  
H(S) ~= 0.639 digits/symbol

## Gibbs' Inequality

If p_1, ..., p_q and p'1, ..., p'q are probability distributions then

-\sum_{i=1}^q p_1 log_r p_i \le -\sum_{i=1}^q p_1 log_r p'i


And

\sum_{i=1}^q p_1 log_r p'i/p_1 \le 0

There is an equality if and only if pi = p'i for all i

## Maximum Entropy Theorem

For any source S with q symbols

H_r(S) \le log_r q

with equality iff all symbols are equally likely ( $H_r(S) = log_r |S|$ )

## First Source-Coding Theorem

For each radix $r$ UD-code $C$ for source $S$, $H_r(S) \le L_r$,
with equality iff $p_i = r^{-l_i} for all $i$ and $K_r = \sum_{i=1}^q r^{-l_i} = 1$

-> K = \sum_{i=1}^q 2^{-l_i} = 1

-> PINK ELEPHANT


## Shannon-Fano Coding

Input: Soruce S = {s_1, ..., s_q} probabilities p_1, ..., p_q
Output: radix r I-code C for S given a decision key

Algorithm::

* Define the codeword lengths l_i = ceil(-log_r(p_i))
* Construct the standard I-code for -l_1, ..., l_q

--
Example
r = 2

Find the probabilities
find the reciprocals (1/p)
Find the smallest power of r, which the reciprocal is smaller than


They give us the lengths of the tree

+ Unlike the huffman encoding scheme, we can quickly know the codeword lengths

## 

H_r(S) \le L_{r,H} \le L_{r,SF} \lt H_r(S) + 1

Huffman - better compression
SF can be used even when only some p_i are known
SF lengths prior to encoding

Worst by at most one.
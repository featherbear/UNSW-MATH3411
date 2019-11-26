---
title: "Lecture 08"
date: 2019-10-11T14:00:27+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

Block symbols - combining multiple symbols 

P(\sigma_i) = P(s_1) * ... * P(S_n)

Assume that they are independent

```
Consider S = {a,b} with P = .75, .25

:: S^2 ::

aa 9/16 0
ab 3/16 11
ba 3/16 100
bb 1/16 101

``` 


Whilst the L values increase for L^n, we then divide by `n` to get the average length



# Markov Sources

A `k`-memory source S is one whose symbols each depend on the previous `k`.

If `k=0` no symbols on any other, S is memoryless
If `k=1` then S is a Markov source

p_ij = P(s_i | s_j) probability of s_i right after a s_j
M = (p_ij) transition matrix - probability of getting from state s_j to state s_i

(INSERT MARKOV MODEL IN NOTES (0:41))

In a transition matrix, the sum of entries of any column in M is 1
let x_k = (s_k;m_k;e_k)  -->

X_k+1 = M x_k
x_k = M^k x_0

x_k = (transition matrix)^k * m_initial

Stable distribution, where Mx_0 = x_0  
-- don't need to find eigenvalues nor eigenvectors

--- stuff I don't need to know ---
A Markov process M is in equilibrium p if p = Mp
 p  is therefore an eigenvector for M with eigenvalue 1

 M is ergodic - can get from any state j to any state i
 M is aperioidc gcd of cycle lengths is 1

---

# Huffman coding for Stationary Markov sources

Consider a source S = {s_1, ... s_q} with probabilities p_1, ..., p_q, transition matrix M and equilibrium p

Huff_E = binary HUffman code on p (ordered)
Huff_(i) = binary Huffman code on the i_th (ordered) column of M
Huff_M: s_1 encoded by Huff_E; for i > 1, s_i encoded by Huff_(i-1)

Average length
* L_E
* L_(1) ... L_(q) --> For each, we create a new tree for the M col i values
* L_M ~= p_1L_(1) + ... + p_qL(q)

L_M <= L_E




Coding and Decoding

Huff_(i) -> Probabilities given that we just had codeword for i

* Start with Huff_E
  * Find the codeword for your symbol
* Use the matrix Huff_(i) (probabilities given the previous symbol)
  * Find the next codeword

To decode, still move left to right

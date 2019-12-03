---
title: "Shannon-Fano Codes"
date: 2019-11-26T11:28:54+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

Each codeword has a length of $\ceil(-\log(p_i))$.

**Don't forget to change base!**

We can then draw the tree, and then fill in the code words.  
(Trees are drawn with the leafs being added as quickly as possible.)


## Average Code Length

Average codeword length: Sum of (probability * code length * number of repetitions)

$ceil(-log(p_i)) * p_i * n$

## Entropy / Limit

$-log(p_i) * p_i * n$  

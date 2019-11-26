---
title: "Lecture Seven"
date: 2019-10-08T12:24:13+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

# Optimising Codeword Efficiency

## Evaluating Usage

**Add the usage of the leaf nodes.**

If not all of the branches are being used ( $K < 1$ ) for some binary code C, we can shorten them.

## 
Assign the smallest codewords to the most frequent symbols

--

## Average / Expected Length

$L = \displaystyle\sum_{i=1}^q p_il_i$

Sum the codeword length multiplied by its probability

## Average Variance

$V = \displaystyle(\sum_{i=1}^q p_il_i^2 ) - L^2$

A UD-code is minimal if it has minimal length

## Minimal

If a binary UD code is minimal

* $l_1 \le l_2 \le ... \le l_q$
* The code may be assumed to be instantaneous
* $K = \sum_{i=1}^q 2^{-l_i} = 1$
* $l_{q-1} = l_q$
* $c_{q-1}$ and $c_q$ differ only in their last coordinate


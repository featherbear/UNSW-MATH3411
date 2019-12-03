---
title: "Bch Codes"
date: 2019-12-03T16:25:25+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

They're like Hamming codes, but this time with algebra (and alphas)

# Single-Error BCH Codes

$C(X) = I(X) + R(X)$

$I(X) === R(X) mod M(X)$

* $C(X)$ - Codeword
* $I(X)$ - Information
* $R(X)$ - Remainder
* $M(X)$ - Minimal polynomial

The first $m$ 'bits' form the check bits, and the last $k$ form the information bits

---
title: "Codeword Extensions"
date: 2019-11-26T16:15:20+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

When dealing with single codewords, we can find the average length of a codeword.  
However, if we have knowledge that we are dealing with groups of codewords, this average length might be less.  

Given code symbols `A`, `B`...  

First/no extension - S^1 -> `A`, `B`
Second extension - S^2 -> `AA`, `AB`, `BB`, `BA`
Third extension - S^3 -> `AAA`, `AAB`, `ABA`, `ABB`, `BAA`, `BAB`, `BBA`, `BBB`

The `n`'th extension will have `a^n` codes, where `a` is the number of single symbols.

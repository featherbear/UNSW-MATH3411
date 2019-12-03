---
title: "Sphere Packing Bound"
date: 2019-12-03T18:44:41+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

The sphere packing bound is a theorem suggesting the largest grouping of codes where no overlap exists.

$|C| \le \frac{2^n}{\displaystyle\sum_{i=0}^t {n \choose i}}$

- When $d$ is odd, $d = 2t - 1$
- When $d$ is even, $d = 2t - 2$

To maximise the number of codewords $|C|$ we want to minimise the error detection capability $t$. This will consequently affect the minimum distance $d\(C)$ / minimum weight $w\(C)$.  
Conversely if we minimise $d$, we maximise $|C|$

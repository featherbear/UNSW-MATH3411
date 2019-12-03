---
title: "Unicity Distance"
date: 2019-12-03T16:00:59+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

![](Screenshot from 2019-12-03 16-01-44.png)

* $q$ - Radix
* $H_q(K)$ - Radix $q$ entropy of $K$
  * $H_q(K) = log_q|K|$
* $K$ - Key space (Number of keys)
* $r_n$ - Average entropy per symbol
  * $r_n = H_q(K_n)/n$
* $d_n = 1 - r_n$

## General Case

$n_0 = \ceil(log_2(|K|) / 3.2)$

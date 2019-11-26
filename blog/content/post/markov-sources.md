---
title: "Markov Sources"
date: 2019-11-26T14:54:12+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

$M$ is the transition matrix  
$P$ is equilibrium distribution matrix (probability vector)

For each column, find the related value in the P matrix, and multiply it by the sum of (probability * log(probability))

Then sum everything

Don't forget to change base if needed - $log(x)/log(b)$


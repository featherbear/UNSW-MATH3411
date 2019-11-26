---
title: "Fermat Factorisation"
date: 2019-11-26T11:41:19+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

# Fermat Factorisation

The Fermat factorisation is a method to find the factors of a large number.  
It is useful when the factors are close to each other, however this method becomes inefficient if the factors are not close.

## Steps

1) Start from $t = \ceil{\sqrt{n}}$  
2) Try get an integer from $s = \sqrt{t^2 - n}$  
3) Else, try get an integer from $s = \sqrt{(t+1)^2 - n}$  
4) ...  
5) Two factors are $(t + s)(t - s)$

Once found, the factors are:  
$a = t + s$  
$b = t - s$

## If you don&apos;t have a calculator

We can expand $(t+1)^2 - n = t^2-n + 2t+1$, and so therefore we can construct a table, and add the previous results to get the next result.
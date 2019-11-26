---
title: "Primitive Roots in Polynomial Space"
date: 2019-11-26T11:55:04+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

This question sucks.

1) Isolate the highest power of the polynomial modulo  
2) If possible, apply the modulo to turn any negative terms into their equivalent positive term  
3) Let $x = \alpha$  
4) Express the powers of alpha in terms of the polynomial modulo
5) If you get a remainder of $1$ for a power that is not $n^p - 1$, try a different alpha substitution ($\alpha+1$ ?!?!)  

# Exponential Arithmetic

- $x^a * x^b = x^{a+b}$
- $(x^a)^b = x^ab$
- $x^{-a} = x^{highestpower - a}

Can express large powers as combinations of smaller powers

* A field has dimension $n$
* A field has $n^p$ vectors

## Example

![](Screenshot from 2019-11-26 11-55-19.png)
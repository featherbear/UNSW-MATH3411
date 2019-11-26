---
title: "Euler's Totient"
date: 2019-11-26T12:13:11+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

Euler's Totient / Phi of $n$ calculates the number of [units](../units) of a given number space $n$

## 1. Factorise `n` into its prime factors  

_eg. $\phi(18) = \phi(2) * \phi(3^2)_  
_eg. $phi(4) = \phi(2^2) = 2^2 - 2^1 = 2$_  

## 2. Apply general formula

> Where $a$ is a prime number, and $b$ the power.  

$\phi(a^b) = a^b - a^{b-1}$  

_e.g._  
_$\phi(2) = 1$_  
_$\phi(3) = 2$_  

---

# Using Euler&apos;s totient

* When gcd(a,m) = 1; a^phi(m) === 1 mod m
* When gcd(a,prime) = 1; a^(prime-1) === 1 mod prime

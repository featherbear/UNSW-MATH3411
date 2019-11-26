---
title: "Kraft McMillan Theorem"
date: 2019-11-26T15:58:00+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

The Kraft-McMillan theorem verifies the possible codeword lengths of a given radix.  
In theory, the sum $K$ of the reciprocal of the radix to the power of each length must be less than or equal to one.

If $K$ is greater than one, then it is impossible for the code to exist.  

We can use this theorem to:

* Verify codeword lengths
* Find other codeword lengths given a value of $K$
* Find the minimum radix given a codeword lengths

## Example

A radix 3 instantaneous code (I-code) has codeword lengths (not necessarily in order) 1,2,3,3,ℓ and Kraft-McMillan coefficient $K = 5/9$

What is the value of ℓ?

**Answer: 3**

1/3 + 1/3^2 + 2*1/3^3 + 1/3^l = 5/9
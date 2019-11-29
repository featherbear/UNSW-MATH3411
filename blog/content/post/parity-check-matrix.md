---
title: "Parity Check Matrix"
date: 2019-11-26T23:35:07+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

# Encoding

* Write the codeword as x1 x2 x3 x4 ... where needed, substitute in the message  
* Multiply H by the codeword, equate each row to 0  
* Solve to find the check-bits  
* Merge  

# Decoding

* Multiply H by the message (as a vector)
* If the resulting vector is
  * Zero vector - no errors, continue
  * Non-zero - Fix the bit associated with the index of the resulting vector in the parity matrix
* Strip check-bits to extract message

- **If the resulting vector is a multiple of one of the columns in the parity matrix, substract the related bit `n` times, such that the resulting vector divides the parity column `n` times.

---

Codewords in a ternary generator matrix: 3^n rows

Codewords in the basis of a binary linear code with parity check matrix H.
(minimum number of elements needed to create all other) (h without the I matrix?)

Greatest number of information bits for a radix 3 2 error linear code with m=5 check bits.

Given a parity check matrix H, the minimum distance d(C) of the code is the minimal weight.

Minimal (Hamming) distance = minimum number of changes == smallest number of linearly dependent columns

> Read [lecture three](../lec03)

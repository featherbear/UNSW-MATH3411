---
title: "Hamming Codes"
date: 2019-11-26T23:38:44+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

Weight - number of non-zero entries in a code

Min Distance = Min Weight

# Binary Hamming Codes

A hamming code $Hamming(n,k)$ has $n$ bits, of which $k$ are information bits.  

Through maths, there are $n-k$ check bits.

There are as many rows as there are checkbits ($n-k$ rows), and as many columns as there are bits ($n$ columns)

For example, $Hamming(7,4)$  

```
1 0 1 0 1 0 1
0 1 1 0 0 1 1
0 0 0 1 1 1 1
```

* $7$ bits
* $4$ information bits
* $3$ check bits

So it a $7$ x $3$ matrix

# Binary Hamming Error-correction

A code $C$ that

- is binary with the code alphabet ${0, 1}$
- has fixed length $n$ codewords $x = x_1 ... x_n$
- is **only single-error correcting**
- provides user-friendly error-correcting
- uses $m$ independent linear parity checks

> Read about [Parity Check Matrices](../parity-check-matrix)  
> Read [lecture three](../lec03)

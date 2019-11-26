---
title: "Huffman Codes"
date: 2019-10-08T12:24:13+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

# Huffman's Algorithm

The Huffman coding scheme generates the best possible uniquely decodable code.  

* All probabilities have to be known before any codeword can be found
* There is no formula for the length of the codewords

* Need to have `n` elements such that `n mod (r-1) === 1`

![](Screenshot from 2019-10-08 13-08-50.png)

## Place-low Strategy

Place $s_{a,b}$ as low as possible

* Combine the two codewords with the lowest probabilities
* Sort the probabilities, placing the combined probability as **low** as possible
* Repeat
* Then label top-down $0, 1, ..., n$

Then trace the tree from the paths

![](Screenshot from 2019-10-08 13-10-18.png)



## Place-high Strategy

Place $s_{a,b}$ has high as possible.

* Combine the two codewords with the lowest probabilities
* Sort the probabilities, placing the combined probability as **high** as possible
* Repeat
* Then label top-down $0, 1, ..., n$

![](Screenshot from 2019-10-08 13-10-43.png)

# Average Length

The usual method to calculate the average length is to sum the product of each codeword's length with its probability.

## Knuth's Theorem

Knuth's theorem allows us to take a short-cut in finding the average length.

> The average codeword length $L$ of each Huffman code is the sum of all child node probabilities / combined nodes
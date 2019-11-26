---
title: "Memory/Markov Sources"
date: 2019-11-26T16:20:21+11:00

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

# Memory Sources

In a `k`-memory source, the probability of the next symbol depends on the last `k` symbols.

## Finding the equilibrium matrix

Find the null space/kernel/(vector that when multiplied by gives zero) of $M - \lambdaI$

# Markov Source

A 1-memory source is also called a Markov source.

## Encoding/Decoding

Start at the equilibrium matrix, and find the code related to the related source message.    
Then find the column related to the previous source message, and find the code related to the next source message.  
etc...

## Entropy

For each column, find the related value in the P matrix, and multiply it by the sum of the (probability*log(probability))'s in that column.

Then sum everything

Don't forget to change base if needed - $log(x)/log(b)$

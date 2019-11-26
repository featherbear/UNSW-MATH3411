---
title: "UD Codes"
description: "Uniquely decodable codes"
date: 2019-11-26T15:43:50+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

UD codes can only be interpreted in one way.  
That is to say, that there is no ambiguity in turning a codeword back into its message.  

> Example One  
&nbsp;  
Code with symbols A: `0` and B: `00`.  
Codeword: `000`  
&nbsp;  
`000` could be translated to `AB`, `BA` or `AAA`.  
Therefore our codes are **NOT** uniquely decodable.

> Example Two  
&nbsp;  
Code with symbols A: `0` and B: `1`.  
Codeword: `010`  
&nbsp;  
Uniquely decodable: `ABA`

> Example Three
&nbsp;  
Code with symbols A: `11`, B: `01`, C: `011`  
Codeword: `011101`  
&nbsp;  
Going left to right, we might be unsure if the first code is `B` or `C`.  
However, the code is still uniquely decodable as we can decode it right to left.  
Message: `BAB`


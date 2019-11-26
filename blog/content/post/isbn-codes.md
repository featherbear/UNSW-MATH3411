---
title: "ISBN Codes"
date: 2019-09-17T12:20:57+10:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

## ISBN

ISBN: **I**nternational **S**tandard **B**ook **N**umber

### 10-digit ISBN

The first 9 bits correspond to the country group, publisher and title. The last bit is used as a check-bit with a character from /[0-9X]/

`(sum i * xi from 1 to 10) = 0`

separate x_10
10 mod 11 === -1 mod 11

`x_10 = (sum i * xi from 1 to 9) % 11`

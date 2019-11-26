---
title: "LZ78 Compression"
date: 2019-11-26T16:35:42+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

LZ78 is a lossless compression algorithm to reduce the size of a repetitive string.

This is done with a dictionary, where previously captured fields can be referenced by their positional index.

**Indexes start at ZERO (0)**

To decode the codeword `(0, c)(0, a)(2, a)(3, b)(4, c)(4, b)`, start with the empty
dictionary.

| output | new dictionary entry |
| :----- | :------------------- |
| c      | 1. c                 |
| a      | 2. a                 |
| aa     | 3. aa                |
| aab    | 4. aab               |
| aabc   | 5. aabc              |
| aabb   | 6. aabb              |

The decoded text is caaaaabaabcaabb

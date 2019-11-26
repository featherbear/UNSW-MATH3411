---
title: "Crypto"
date: 2019-11-13T13:47:13+11:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

* Caesar Cipher - Simple modulo rotation of each letter
  * ABCD ->3-> DEFG
* Monoalphabetic substitution cipher
  * ABAB ->XY-> XYXY
* Transposition cipher
  * HELLO ->2-> LOHEL
* [Vigenere cipher](https://featherbear.github.io/UNSW-COMP6441/blog/post/the-vigenere-cipher/)
  * HELLO ->SECRET-> ZINCS
* [One-time pad / Vernam cipher](https://featherbear.github.io/UNSW-COMP6441/blog/post/one-time-pads/)
  * OP.

## Feedback Ciphers

When the key is not long enough to encipher the entire plaintext message, we can use extra data as the key

### Plaintext Feedback

Uses the plain text as extra letters for the key.

### Ciphertext feedback

Uses the cipher result as extra letters for the key,

### External Source
... eh.


# Analysing / Breaking Ciphers

## Kasiski's Method

_Kasiski's method helps to find a key length / period._

Read: [Index of Coincidence](https://featherbear.github.io/UNSW-COMP6441/blog/post/index-of-coincidence/)

$P_C(m) ~= I_c(m) = \Sum (f_i ; 2 ) / (n ; 2) = (\Sum f_i^2 - n) / (n^2 - n) $

((Sum of the square of each frequency) - #elems) /  (#elems^2 - #elems)

So the number of pairs is 1/2 n (n-1) I_c

## Cipher Mechanisms

* Stream ciphers - One symbol at a time
* Block ciphers - Groups of symbols at a time
* Product ciphers - Cipher output is re-enciphered again

---

One way functions:  

* Given $x$, easy to find $f(x)$.
* With only $f(x)$, hard to find $x$

One way hash functions:

* Function is a one-way function
* Takes a message of any length and maps to a fixed length
* Given x, hard to find x' where f(x) = f(x')

One way trapdoor function:

* Function is a one-way function
* Given f(x) and some extra information, easy to find x

---

## Symmetric Cryptography

Same key used to encrypt and decrypt

[Diffie-Hellman](https://featherbear.github.io/UNSW-COMP6441/blog/post/lec13/#diffie-hellman) can be used to private share a secret with a recipient, which can _then_ be used to generate a secret.

(Diffie-Hellman is for **key exchange**, not secure communication)

## Asymmetric Cryptography

One key (public key) for encrypting, one key (private key) for decrypting.  

Only the owner has the private key, whilst anyone can hold the public key.

* [RSA](https://featherbear.github.io/UNSW-COMP6441/blog/post/rsa-crypto/)
* McEliece Encryption (1978)

---

## Digital Signatures

Read: [Signing](https://featherbear.github.io/UNSW-COMP6441/blog/post/lec10/#signing-documents)

Sign by encrypting with private key. Receiver decrypts with public key.



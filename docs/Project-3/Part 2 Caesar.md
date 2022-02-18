---
parent: Project 3&#58 Wordy
math: katex
nav_order: 1
---

# Part 2 Caesar

Write a function that encrypts a message using Caesar's cipher.

## Background

Supposedly, Caesar used to "encrypt" (i.e., conceal in a reversible way) confidential messages by shifting each letter therein by some number of places. For instance, he might write A as B, B as C, C as D, …, and, wrapping around alphabetically, Z as A. And so, to say `HELLO` to someone, Caesar might write `IFMMP`. Upon receiving such messages from Caesar, recipients would have to "decrypt" them by shifting letters in the opposite direction by the same number of places.

The secrecy of this "cryptosystem" relied on only Caesar and the recipients knowing a secret, the number of places by which Caesar had shifted his letters (e.g., 1). Not particularly secure by modern standards, but, hey, if you’re perhaps the first in the world to do it, pretty secure!

Unencrypted text is generally called *plaintext*. Encrypted text is generally called *ciphertext*. And the secret used is called a *key*.

| **plaintext**    | H    | E    | L    | L    | O    |
| ---------------- |:----:|:----:|:----:|:----:|:----:|
| **+ key**        | 1    | 1    | 1    | 1    | 1    |
| **= ciphertext** | I    | F    | M    | M    | P    |

More generally, Caesar’s algorithm (i.e., cipher) encrypts messages by "rotating" each letter by *k* positions. More formally, if *p* is some plaintext (i.e., an unencrypted message), *p* is the $i^{th}$  character in *p*, and *k* is a secret key (i.e., a non-negative integer), then each letter, $c_i$ , in the ciphertext, *c*, is computed as
$$
c_i \equiv(p_i+k) \mod 26
$$
wherein $\mod 26$ here means "remainder when dividing by 26." This formula perhaps makes the cipher seem more complicated than it is, but it’s really just a concise way of expressing the algorithm precisely.

## Specifications

Write a function `caesar` that encrypts a message using Caesar's cipher.

- The function should take two parameters, `message` and `k`, where `k` is the rotation.
- The function should return the ciphertext.
- Do not assume that *k* will be between 1 and 26. Your program should work for any integer. But, even if *k* is greater than 26,  alphabetical characters in your program’s input should remain alphabetical characters in your program’s output. For instance, if *k* is 27, `A` should not become `[`even though `[` is 27 positions away from `A` in ASCII, per [asciichart.com](http://www.asciichart.com/); `A` should become `B`, since `B` is 27 positions away from `A`, provided you wrap around from `Z` to `A`.
- Your program must preserve case: capitalized letters, though rotated, must remain capitalized letters; lowercase letters, though rotated, must remain lowercase letters.
- Digits, symbols, and spaces are not encrypted.
- Code is well-documented.

## Examples

```python
>>> caesar("HELLO", 1)
IFMMP
>>> caesar("Hello, World!", 13)
Uryyb, Jbeyq!
>>> caesar("be sure to drink your Ovaltine", 39)
or fher gb qevax lbhe Binygvar
>>> caesar("", 10)	# returns empty string

# Input guards
>>> caesar(12, 1)
Invalid plaintext
>>> caesar("hello", "1")
Invalid key
```

# Vigenère

Write a function that encrypts a message using Vigenère's cipher.

## Background


Vigenère’s cipher improves upon Caesar’s cipher by encrypting messages using a sequence of keys (or, put another way, a keyword). In other words, if p is some plaintext and k is a keyword (i.e., an alphabetical string, whereby A represents 0, B represents 1, C represents 2, …, and Z represents 25), then each letter, , in the ciphertext, c, is computed as:
$$
c_i \equiv (p_i + k_j) \mod 26
$$
Note this cipher’s use of $k_j$ as opposed to just *k*. And if *k* is shorter than *p*, then the letters in *k* must be reused cyclically as many times as it takes to encrypt *p*.

In other words, if Vigenère himself wanted to say HELLO to someone confidentially, using a keyword of, say, ABC, he would encrypt the H with a key of 0 (i.e., A), the E with a key of 1 (i.e., B), and the first L with a key of 2 (i.e., C), at which point he’d be out of letters in the keyword, and so he’d reuse (part of) it to encrypt the second L with a key of 0 (i.e., A) again, and the O with a key of 1 (i.e., B) again. And so he’d write HELLO as HFNLP.

| **plaintext**    | H    | E    | L    | L    | O    |
| ---------------- | ---- | ---- | ---- | ---- | ---- |
| **+ key**        | A    | B    | C    | A    | B    |
| **(key as #)**   | 0    | 1    | 2    | 0    | 1    |
| **= ciphertext** | H    | F    | N    | L    | P    |

## Specification

Write a function `vigenere` that encrypts a message using Vigenère's cipher.

- The function should take two parameters, `message` and `key`.
- The function should return the ciphertext.
- Your program must preserve case: capitalized letters, though rotated, must remain capitalized letters; lowercase letters, though rotated, must remain lowercase letters.
- Digits, symbols, and spaces are not encrypted.
- Code is well-documented.

## Examples

``` python
>>> vigenere("hello", "abc")
hfnlp
>>> vigenere("Meet me at the park at 11 am", "bacon")
Negh zf av huf pcfx bt 11 ca
>>> vigenere("", "abc") # returns empty string

# Input guards
>>> vigenere("hello", 1) # key shouldn't be more than one word
Invalid key
```

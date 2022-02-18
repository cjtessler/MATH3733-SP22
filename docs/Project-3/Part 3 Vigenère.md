---
parent: Project 3&#58 Wordy
math: katex
nav_order: 1
---

# Part 3 Vigenère

Write a function that encrypts a message using Vigenère's cipher.

## Background

Vigenère’s cipher improves upon Caesar’s cipher by encrypting messages using a sequence of keys (or, put another way, a keyword). In other words, if p is some plaintext and k is a keyword (i.e., an alphabetical string, whereby `A` represents `0`, `B` represents `1`, `C` represents `2`, …, and `Z` represents `25`), then each letter, $$p$$, in the ciphertext, $$c$$, is computed as:

$$
c_i \equiv (p_i + k_j) \mod 26
$$

Note this cipher’s use of $k_j$ as opposed to just *k*. And if *k* is shorter than *p*, then the letters in *k* must be reused cyclically as many times as it takes to encrypt *p*.

In other words, if Vigenère himself wanted to say `HELLO` to someone confidentially, using a keyword of, say, `ABC`, he would encrypt the `H` with a key of 0 (i.e., A), the E with a key of 1 (i.e., B), and the first L with a key of 2 (i.e., C), at which point he’d be out of letters in the keyword, and so he’d reuse (part of) it to encrypt the second L with a key of 0 (i.e., A) again, and the O with a key of 1 (i.e., B) again. And so he’d write `HELLO` as `HFNLP`.

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

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

Write a function `caesar(text: str, k: int) -> str` that encrypts a message using Caesar's cipher.

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

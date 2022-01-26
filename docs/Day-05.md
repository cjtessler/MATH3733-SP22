---
math: katex
---

# Day 05

## A Discussion about floats

Class have **methods** associated with them. They are functions attached to a **class**.

``` python
>>> type(3.14)
<class 'float'>
>>> (-2.0).is_integer()
True
>>> (3.2).is_integer()
False
```

Weird bugs can be introduced when working with floats.

``` python
x = 0
inc = 0.1

# Add to one by tenths
for i in range(10):
    x = x + inc

if x == 1.0:
    print(f"{x} is == 1.0")
else:
    print(f"{x} is not 1.0")

# 0.9999999999999999 is not 1.0
```

When comparing floats, check that the error is less than some epsilon.

``` python
x = 0
inc = 0.1
epsilon = 0.01

# Add to one by tenths
for i in range(10):
    x = x + inc

if abs(1.00 - x) <= epsilon:
    print(f"{x} is almost 1.0")
else:
    print(f"{x} is not 1.0")

# 0.9999999999999999 is not 1.0
```

Another way we can avoid the error using **discretization**.

> In applied mathematics, discretization is the process of transferring continuous functions, models, variables, and equations into discrete counterparts. This process is usually carried out as a first step toward making them suitable for numerical evaluation and implementation on digital computers.

``` python
x = 0   # if you declare x as an int, you don't need to cast it below
inc = 0.1
is_discretized = False  # this is a flag

# discretize to two place values
if isinstance(inc, float):
    is_discretized = True
    inc = int(inc * 100)

# Add to one by tenths
for i in range(10):
    x = x + inc

if is_discretized:
    x = x / 100

if x == 1.0:
    print(f"{x} is == 1.0")
else:
    print(f"{x} is not 1.0")

# outputs 1.0 is == 1.0
```

## Floating Point Errors Explanation

Represent the number 302 using expanded notation.

$$3 \times 10^2) + (0 \times 10^1) + (2 \times 10^0)$$

A sequence of length $n$ can represent $10^n$ different numbers.

Computers use *binary* (base 2). A binary number is represeneted by a sequence of digits each which is either 0 or 1. The digits of a binary number are often referred to as **bits**.

$$101_2 = (1 \times 2^2) + (0 \times 2^2) + (1 \times 1) = 5$$

What is is that decimal equivalent of the binary number `10011`? 1 + 2 + 16

We can represent a decimal using the significant digits of a number and a exponent. For example 1.949 would be represented as the pair (1949, -3), which stands for $$1949 \times 10^{-3}$$.

The number 0.625 (5/8) woud be represented by (101, -11), which is $$5 \times 2^{-3}$$.

What about 1/10 (0.1)? With four bits we could do 0.09375 (3/32) as (0011, -0101), which is $$3 \times 2^{-5}$$.

Most implementations of Python use 53 bits of precision.

## Finding The Sqaure Root

### Method 1: Exhaustive Enumeration / guess-and-check

``` python
# Find the square root of a perfect square
x = int(input())
num_guesses = 0
guess = 0

# increment guess until its square is at least as large as the input being checked
while guess ** 2 < x:
    num_guesses += 1
    guess += 1
print(guess)

# check if the input is a perfect square
if guess ** 2 != x:
    print(x, "is not a perfect square")
else:
    print(f"The square root of {x} is {guess}")

print(f"The algorithm took {num_guesses} guesses")
```

This algorithm wll take 35,137 guesses to determine if 1,234,567,890 is a perfect square. Bisection search will take 51 guessues - and actually compute the value of the square root.

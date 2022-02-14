---
parent: Lessons
nav_order: 1
---

# Day 01: Computing Terminology, Arithmetic Operators

## What is a "computer"?

- The machine in front of you is a *modern* computer.
- A computer is one who computes.
- You are a computer!
- By today’s standards you are a slow computer with bad memory… but necessary to design and implement modern computers.
- We need tools to aid in our computation as we move into the future

## What does a computer do?

- Performs calculations
- Remembers calculations
- What a human tells it to do

> “What I mean is that if you really want to understand something, the best way is to try and explain it to someone else. That forces you to sort it out in your own mind... And that’s really the essence of programming. By the time you’ve sorted out a complicated idea into little steps that even a stupid machine can deal with, you’ve certainly learned something about it yourself.”

> ― Douglas Adams, Dirk Gently's Holistic Detective Agency

## Terminology

**Computation** is any type of calculation that includes both arithmetical and non-arithmetical steps and which follows a well-defined model (e.g. an **algorithm**).

A **program** is a sequence of instructions that specify how to perform a computation.

## guessing game

``` text
I am thinking of a number! Try to guess the number I'm thinking of: 10
Too low! Guess again: 100
Too high! Guess again: -100
Too low! Guess again: 95
That's it! Would you like to play again? (yes/no) 
```

Main Ideas

- *variables* to store numbers
- *conditionals* or *branching* to test guess
- input/output
- repetition (looping)
- numbers (ints, floats, etc)
- words (strings)
- actions (functions)
- implementing further features such as randomness

We will eventually build this, take care of errors, and improve gameplay.

## REPL

A **Read-Eval-Print Loop (REPL)**, also known as an interactive shell, is a simple, interactive computer programming environment that takes single user inputs (READ) (i.e. single expressions), EVALUATES them, and returns (PRINTS) the result to the user; a program written in a REPL environment is executed piecewise.

## Arithmetic Operators

[Official Python Docs: 3.8 Using Python as a Calculator](https://docs.python.org/3.8/tutorial/introduction.html#using-python-as-a-calculator)

Arithmetic operators follow standard order of operation

- `()` : parentheses
- `**` : exponentiation
- `+` : addition
- `-` : subtraction
- `*` : multiplication
- `/` : division

## calculator (interactive)

``` python
>>> 3 + 3
6
>>> (3 + 6) ** 2
81
>>> 5 / 2
2.5
>>> 100 / 50 - 1
1.0
```

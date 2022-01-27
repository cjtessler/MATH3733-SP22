# Day 04

## Announcements

- Exercise 03 is due tonight
- Exercises 04 - 10 is due next Wednesday, midnight. These will solidy the concepts from the week, and will help you on project 1.

## Followup about `input`

The `input` function does NOT need an argument. E.g.

``` python
x = int(input())
print(f"You entered {x}")
```

## Chained Conditionals

```python
# compare.py
x = 5
y = 6

# The first branch that evaluate to True runs, and then the rest of the branches are ignored.
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')

print("I am done comparing!")
```

No limit on number of branches.

## Nested Execution

Identation is important in Python as it creates blocks of code.

```python
if x == y:
    print('x and y are equal')
else:
    if x < y:
        print('x is less than y')
    else:
        print('x is greater than y')

# Equivalently... 
if x == y:
    print('x and y are equal')

if x < y:
    print('x is less than y')
else:
    print('x is greater than y')
```

The second approach above is preferred because it has less indentation.

```python
if 0 < x:
    if x < 10:
        print('x is a positive single-digit number.')
 
if 0 < x and x < 10:
    print('x is a positive single-digit number.')
    
if 0 < x < 10: # not available in all languages
    print('x is a positive single-digit number.')
```

## Guessing Game

```python
# guess.py
target = 55
guess = int(input("I am thinking of a number! Try to guess the number I'm thinking of: "))

if target == guess:
    print("That's it!")
else:
    print("Nope!")
```

## Iteration with `while`

`while` loops are good when when we do not know long we need to wait

[![While Lop](https://upload.wikimedia.org/wikipedia/commons/4/43/While-loop-diagram.svg)](https://upload.wikimedia.org/wikipedia/commons/4/43/While-loop-diagram.svg)

```python
target = 55
guess = int(input("I am thinking of a number! Try to guess the number I'm thinking of: "))

while guess != target:
    guess = int(input("Try again: "))
        
print("That's it!")
```

```python
# stuck.py
n = 0
while n < 5:
    print(f"{n} is less than 5. You're stuck!)    
```

Use Ctrl + C on Windows or Cmd + C on Mac to KeyboardInterrupt execution.

```python
n = 0   # n is a counter variable, and it and is declared outside of the loop
while n < 5:
    print(n)
    n = n + 1
```

## `break`

`break` is used to get out of a loop.

Find a positive integer that is divisible by both 11 and 12

The following algorithm is using "exhaustive enumeration"... it's slow... and exhausting.

``` python
x = 1 
while True:
    print("Checking", x)
    if x % 11 == 0 and x % 12 == 0: 
        break 
    x = x + 1 

print(x, 'is divisible by 11 and 12') 
```

## Exercise

Find the THIRD positive integer that divisible by both 11 and 12 using an exhaustive enumeration algorithm.

### Solution

``` python
x = 1
encountered = 0

while True:
    print("Checking", x)
    if x % 11 == 0 and x % 12 == 0: 
        encountered += 1  

        if encountered == 3:
            break

        x = x + 1 

print(x, 'is divisible by 11 and 12') 
```

## For Loops

```python
for n in range(5):
    print(n)
```

`range(5)` creates the sequence 0, 1, 2, 3, 4 and `n` takes on each value for each time through the loop

## `continue`

`continue` is used to skip a particular case in a loop

```python
for n in range(5):
    if n == 4:
        continue
    print(n)
```

## Exercises

Compute the sum of the first 12,345,678 square integers.

### Solution

```python
total = 0

for i in range(12_345_678):
    total += i ** 2

print(total)
```

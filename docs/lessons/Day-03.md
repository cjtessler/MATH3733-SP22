---
parent: Lessons
---

# Day 03

## Recommendations

- Exercises 00 through 02 are due tonight!
- Read through Project 1 description
  - You should should be able to complete Part 2 after we discuss `while` loops
  - Part 1 has some sneaky bugs that might be easier to solve after we discuss **floating point errors** on Friday.
  - Regardless, it is still a good idea to begin solving the problems.
  - Try to work out the solution by hand first.

## Data Types

A value is a basic object that that program works with. We can use the `type()` function to determine the type of a value.

```python
>>> type(2) 
<class 'int'>

>>> type(42.0) 
<class 'float'>

>>> type('Hello, World!') 
<class 'str'>

>>> # Data Type Converstion
>>> price = "1.99"
>>> type(price)
<class 'str'>

>>> real_price = float(price)
>>> type(real_price)
<class 'float'>

>>> float_to_int = int(real_price)
>>> float_to_int
1
```

Appropriate data type can be **cast** to another data type using functions:

- `int()`
- `float()`
- `str()`

## input.py

```python
your_name = input("what is your name?")
print("Hello", your_name)

your_age = input("How old are you?")
print(f"You are {your_age} years old.")

older_age = your_age + 1
# the input() function returns a string
type(your_age)

# convert a string to an int using the int() function
older_age = int(your_age) + 1
print(f"Next year you will be {older_age}.”)

older_age = older_age + 1
print(f"In two years you will be {older_age}.”)

older_age += 1  # shorthand for older_age = older_age + 1
print(f"In three years you will be {older_age}.”)
```

### A caution about input

```python
>>> input = input("Enter your name: ")  # input is a function here
Enter your name: Cody
>>> input
'Cody'
>>> input = input("Change your name: ")
Traceback (most recent call last):
  File "<pyshell#3>", line 1, in <module>
    input = input("Change your name: ")
TypeError: 'str' object is not callable
>>> 
```

The programmer overwrote Python's implementation of the `python` with their own value.

## Exercise

Write a program to compute the area of a circle. There will be three variables `pi`, `radius`, and `area`. Choose an appropriate value for `pi`, ask the user for `radius`, and then `area` should be computed appropriately. Print the area.

### Exercise 2 Solution

```python
pi = 3.14
radius = int(input("Enter a value for the radius: "))
area = pi * (radius ** 2)
print(area)
```

## Other Math Operations

- // : integer division (applies floor function after division)
- % : modulo

```python
# division returns a float
print(4 / 2)    # 2.0, float
print(3 / 2)    # 1.5, float

# integer division returns an int by droppng the frational part
print(4 // 2)   # 2, int
print(3 // 2)   # 1, int

# examples of modulo operator %
# a % b -> remainder when a is divided by b
print(3 % 2)        # 13 mod 2 = 1
print(11 % 3)       # 11 mod 3 = 2
print(20 % 7)       # 6
```

## Boolean Expressions

A **boolean expression** is an expression that is either true or false.

The double equal sign `==` is the comparison opeartor.

```python
>>> 5 == 5
True
>>> 5 == 6
False
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
>>> bool(0)
False
>>> bool(1)
True
>>> bool("hello")
True
>>> bool(None)
False
>>> bool(42)
True
```

## Comparison Operators

```python
>>> x = 5
>>> y = 6
>>> 
>>> # == is the comparison operator
>>> #  = is the assignment operator
>>>
>>> print(x == y)
False
>>> print(x != y)   # not equal
True
>>> print (x > y)
False
>>> print(x < y)
True
>>> print(x <= y)
True
>>> print(x >= y)
False
>>> 
>>> ## String Comparisons
>>> s1 = "abb"
>>> s2 = "abc"
>>> 
>>> print(s1 == s2)
False
>>> print(s1 < s2)
True
>>> print(s2 > s1)
True
>>> # String comparison is done by lexographical ordering
>>> 
>>> # strings and ints cannot be compared
>>> print("a" > 5)
Traceback (most recent call last):
  File "<pyshell#24>", line 1, in <module>
    print("a" > 5)
TypeError: '>' not supported between instances of 'str' and 'int'
```

## Logical Operators

Let `a` and `b` be variable names with Boolean values.

| **a** | **b** | **not a** | **a and b** | **a or b** |
| --- | --- | --- | --- | --- |
| True | True | False | True | True |
| True | False |     | False | True |
| False | True | True | False | True |
| False | False |     | False | False |

```python
>>> not True
False
>>> not False
True
>>> True and True
True
>>> True and False
False
>>> True or True
True
>>> True or False
True
```

## Control Flow / Branching

```python
# branch.py

x = int(input("Can I have an x please?"))
# Consider 5, -1, 0

if x > 0:
    print('x is positive')
```

## Alternative Execution

``` python
x = int(input("Can I have an x please?" ))

if (x > 0):
    print(f"{x} is positive!")
elif x == 0:
    print(f"Good compromise! {x} is neither positive nor negative")
else:
    print(f"fine... {x} is negative...")
```

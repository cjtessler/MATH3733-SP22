---
parent: Lessons
---

# Day 02: Variables

## Debugging

Demonstrate `print(“hello world”)` in interactive mode.

``` python
>>> print(“hello world!”)
hello world
```

- `print(arguments)`  is a function
- We *call* a function and it performs actions
- “Hello world” is a string (data type)
- Let’s break the program. Below are a few examples.

``` python
>>> print("Hello World"
... )
# It is expecting the closing parentheses 

>>> print("Hello World)
# SyntaxError: EOL while scanning string literal
# EOL mean "End of line"
# The Python interpreter was looking for the end of string, the closing "

>>> prin("Hello world")
# NameError: name 'prin' is not defined
# "prin" is not a defined function
# We will learn how to define our own functions in the future
        
>>> print(hello world)
# SyntaxError: invalid syntax

>>>   print("Hello World!")
# IndentationError: unexpected indent
# Python use whitespace to determine "blocks" of code
# More on this later
```

- An error in a program is known as a “bug”.
- [The First Computer Bug Ever Found! | Technology Facts - Glitch Facts - YouTube](https://www.youtube.com/watch?v=84VmwdGwYMA)
- The process of fixing fixing bugs is known as **debugging**.
- Read the error messages!

## hello_variables.py

A small program is sometimes referred to as a *script*.

```python
print("Hello World"
# SyntaxError: unexpected EOF while parsing
# EOF means "End of file"
# The Python interpreter was expecting the closing )
```

A **variable** is a name that refers to an object.

The `=` is the assignment operator.

Notice that variable names can be more than single letters.

```python
# "comments" are preceded by a hash character
# Used to to clarify code and are not interpreted by Python
"# This is not a comment because it's inside quotes." 
# It is a string

m = "Hello variables"
print(msg)

# variables should be descriptive
message = "My message"
print(message)

# variable referring to numbers
print(7)
my_number = 1
print(my_number)

your_number = 14
our_number = my_number + your_number
print(our_number)

# print function with multiple arguments
first_name = "Cody"
last_name = "Tessler"
print(first_name, last_name)

# variables can be reassigned
first_name = "Hayley"
print("first_name has been changed")
print(first_name, last_name)

# print function with sep argument
print("Today's date is")
print(1, 22, 2018, sep='/')
print() # adds an extra line

# f-strings are convenient for string interpolation
print("My first name is ", first_name, ", and my last name is ", last_name)
print(f"My name is {first_name} and my last name is {last_name}")
```

The `print()` function can take more than one argument.  It concatenates the strings. [2. Built-in Functions — Python 3.8 documentation](https://docs.python.org/3.8/library/functions.html#print)

## Exercise

Write a program to compute the radius of a circle. There will be three variables `pi`, `radius`, and `area`. Choose an appropriate value for `pi`, a value of your coice for `radius`, and then `area` should be computed appropriately. Print the area.

``` python
pi = 3.14
radius = 10
area = pi * (radius ** 2)
print(area)
```

## Rules for variables

- No spaces. Use underscore in place of a space
  - `my var` is not valid
  - `my_var` is valid

---

- The first character of a variable name must be a letter or the underscore character.
  - `4var` is invalid
  - `_message` is valid

---

- No characters are allowed in a variable name besides alphanumeric (alphabet or numeric) characters and the underscore ("_") character (no special characters like &, !, +, $, etc.)
  - `you&i` is invalid
  - `you_and_i` is valid

---

- Python is case sensitive, so two variables with the same name but different case are two different variables
  - `name`, `NAME`, and `Name` are all different variables

---

- You can't use any of Python's built in "reserved words” or *keywords* (i.e. you can't create a variable called "print" because that would conflict with the print function).

``` python
>>> import keyword
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

## Strings

- A **character** is a letter, special character, space, or digit.
- A **string** is a sequence of characters.

``` python
>>> "hello world"
'hello world'
>>> 'hello world'
'hello world'
>>> mystic_creature = "dragon"
>>> annoying_bug = "fly"
>>> print(mystic_creature + annoying_bug)
'dragonfly'
```

String Operations:

- Addition is concatenation
- Multiplication is repetition
- Subtraction and division are unsupported (try subtracting strings)

## na_song.py

[Na Na Na Na Hey Hey-ey Goodbye](https://www.youtube.com/watch?v=IoyvvEWHodk&ab_channel=AnilVitaliSekharNaik)

``` python
l1 = "na"
l2 = "hey"
l3 = "goodbye"

print(l1 * 4 * 2, l2 * 3, l3, sep=" ") # print "nananananananana heyheyhey goodbye"
```

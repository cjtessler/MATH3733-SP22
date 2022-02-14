# Day 13

## Immutability

Strings are immutable, which means they CANNOT be changed once defined.

``` python
# immutable == can't change
greeting = 'Hello, world!'

# Change the first letter to a J
greeting[0] = 'J' # TypeError: 'str' object does not support item reassignment
greeting = 'J' + greeting[1:]
```

## Searching

``` python
### Searching
def find(word, letter):
    index = 0
    while index < len(word):
        if word[index] == letter:
            return index
        index += 1
    return -1

print(find('banana', 'n')) # prints 2
print(find('banana', 'h')) # prints -1

# Exercise: Generalize the function so that it has a third parameter, the index in the word where it should start looking
def indexed_find(word, letter, start):
    index = start
    while index < len(word):
        if word[index] == letter:
            return index
        index += 1
    return -1

print(indexed_find('banana', 'n', 3)) # prints 4
print(indexed_find('banana', 'h', 3)) # prints -1
```

## Looping and Counting

``` python
## Looping and Counting
counter = 0
for letter in 'banana':
    if letter == 'a':
        counter += 1
print(counter) # prints 2

# Exercise: Encapsulate this logic into a function called count
def count(word, l):
    counter = 0
    for letter in word:
        if letter == l:
            counter += 1
     return counter
 
print(count('banana', 'a')) # prints 2
```

## Escape Characters

``` text
>>> print("We are the so-called "Vikings" from the north.")
  File "<stdin>", line 1
    "We are the so-called "Vikings" from the north."
                           ^
SyntaxError: invalid syntax

>>>  print("We are the so-called \"Vikings\" from the north.")
We are the so-called "Vikings" from the north.

>>> print("The only problem\nwith haiku is you just get\nstarted and then you")
The only problem
with haiku is you just get
started and then you
```

## String Methods

``` python
# https://docs.python.org/3/library/stdtypes.html#string-methods
word = 'banana'

# upper
new_word = word.upper() # we are 'invoking' upper on word
print(new_word) # prints 'BANANA'
print(word) # string methods do not change the string, they return a new string

# find
index = word.find('a')
print('a is at index', index)

# this function is more general that ours
index = word.find('na')
print('na begins at index', index)

# Exercise: Peruse the string methods in the docs. What does strip and replace do?
word = "help!!!!!!!!!!!!"
print(word.rstrip('!')) # prints 'help'
print(word.replace('!', '.'))

# isX methods return a Boolean
'1'.isalpha() # False
'1'.isdigit() # True
'a'.islower() # True
'A'.isupper() # True
```

## Comparison

``` python
# The 'in' operator
print('a' in 'banana') # True
print('l' in 'banana') # False


# comparison
print('A' == 'a') # False
print('A' < 'a')  # True

# order
# http://www.asciichart.com/
print(ord('A'))	# 65
print(ord('a'))	# 97
print('#' < 'a') # True. why?

# chr
print(chr(65)) # A
print(chr(97)) # a
```

## Star Wars ASCII

[https://youtu.be/Dgwyo6JNTDA](https://youtu.be/Dgwyo6JNTDA)
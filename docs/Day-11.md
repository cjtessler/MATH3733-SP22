# Day 11

## Strings

A string is a sequence of characters.

## Indexing

``` python
## The "index" is a location in a string.
## Python strings are zero indexed (the first character is at index 0)
# positive indexing
fruit = 'banana'
letter = fruit[1]
print(letter) # prints 'a'
# the expression in the bracket is the index, it begins at 0
print(fruit[0]) # prints 'b'

# indexing backwards
print(fruit[-1]) # prints 'a'
print(fruit[-4]) # prints 'n'
```

## `len()`

``` python
length = len(fruit)	# careful to not use len as variable
print(length) # prints 6
print(fruit[length]) # IndexError: string index out of range
print(fruit[length-1]) # prints 'a'
```

## Iteration (String transversal)

``` python
## transversal with a while loop
index = 0
while index < len(fruit):
    letter = fruit[index]
    print(letter)
    index += 1
    
## transversal with a for loop
for index in range(len(fruit)):
    print(fruit[index]
          
# If we do not need the index, we can iterate through the characters directly         
for ch in fruit:
    print(ch)

# If we need the index and don't like range(len(fruit))
# use enumerate (this is considered "pythonic")
for i, ch in enumerate(fruit):
    print(i, ch)
```

## Pythonic

``` python
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

## String Slicing

``` python
s = 'Monty Python'
first = s[0:5] 
print(first) # prints 'Monty'
# 0 <= i < 5

second = s[6:12]
print(second) # prints 'Python'

print(s[:3]) # prints 'Mon'
# if no starting index is given, defaults to 0
print(s[10:]) # prints 'on'

# Exercise: Print the space
print(s[5:6])
```

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

>>> print("The only problem\nwith haiku is you just get\nstarted and then")
The only problem
with haiku is you just get
started and then
```

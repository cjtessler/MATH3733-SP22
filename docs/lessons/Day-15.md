---
parent: Lessons
---

# Day 15: More on Lists, Tuples, Comprehensions

## Removing elements

``` python
c = [1, 2, 3]

# Remove a specific item
my_list = c[:] # makes a copy of c called my_list
my_list.remove(1)
print(my_list)
print(c)

# Aliasing
# The association of a variable with an object is called a reference.
# In this example there are two references to the same object
alias_list = c # make an alias for c called alias_list
alias_list.remove(1)
print(c)

# Trying to remove an element that is not in the list raises an error
c.remove(4) # Error
if 4 in c:
    c.remove(4)
 
# Removing an item by index
del c[0]    # del is an operator
print(c)

# Remove and store the item in a variable using the pop method
value_at_zero = c.pop(0)
print(c)
print(value_at_zero)
```

See [PythonTutor Example of Aliasing](https://pythontutor.com/visualize.html#code=%23%20Initialize%20list%20c%0Ac%20%3D%20%5B1,%202,%203%5D%0A%0A%23%20Copy%20list%20c%0Amy_list%20%3D%20c%5B%3A%5D%0A%0A%23%20Remove%201%20from%20my_list%0Amy_list.remove%281%29%0A%0A%23%20Create%20an%20alias%20to%20list%20c%0Aalias_list%20%3D%20c%0A%0Aalias_list.remove%281%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false).

## Various Methods

``` python
# sort method
my_list = [9, 3, 11]
my_list.sort()          # modifies original list
print(my_list)          # [3, 9, 11]


# sorted function
my_list = [9, 3, 11]
print(sorted(my_list))  # returns a copy that is sorted
print(my_list)          # [9, 3, 11]

my_list.reverse()       # modifies original list
print(my_list)          # [11, 3, 9]


# index
my_list = [9, 3, 11]
print(my_list.index(3)) # 1
print(my_list.index(5)) # ValueError


# extrema
print(min(my_list))     # 3
print(max(my_list))     # 9


# split
text = "Hello world!"
words = text.split()
print(words)            # ['Hello', 'World!']

scores = '90,67,87,102,77,80'
nums = scores.split(',')
print(nums)             # ['90', '67', '87', '102', '77', '80']


# list
letters = list("hello") 
print(letters)          # ['h', 'e', 'l', 'l', 'o']
print(list(range(10)))  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(10))         # # TypeError: 'int' object is not iterable


# join (string method)
"".join(letters)        # 'hello'
```

## Exercise

``` python
# Exercise: Grocery List Input
# Write a function make_grocery_list
# Adds grocery items to a list as they are input, until the user enters "done".
# Prints the sorted list

def make_grocery_list():
    # initialize empty list
    grocery_list = [] 
    item = ""

    # adds items to list
    while item != 'done':
        item = input('Enter a grocery item or "done": ')
        grocery_list.append(item) # add to list

    # delete "done"
    grocery_list.pop(-1)

    # organize list alphabetically
    grocery_list.sort() 

    print()
    
    for item in grocery_list:
        print(item)


make_grocery_list()
```

## Nested List

``` python
##### Nested Lists #####
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

matrix = [[1, 2, 3],    # Cleaner code
          [4, 5, 6],
          [7, 8, 9]]

print(matrix[1][1])     # 5
```

## Tuples

``` python
##### Tuples #####

# Tuples are essentially immutable lists.
dimensions = (1920, 1080)
print(dimensions[0])
print(dimensions[1])
dimensions[0] = 1080 # TypeError

# reassign a tuple by overwriting it
dimensions = (1280, 720)
```

## Comprehensions

``` python
##### List Comprehensions #####

my_squares = []
for x in range(10):
    my_squares.append(x**2)
    
print(my_squares)   # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# Syntax: [var_expression for var in iterable if condition]
# if condition is optional

# {x^2 : x in [0, 9)}
my_squares = [x**2 for x in range(10)]
print(my_squares)   # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]


# Exercise: Generate a list of the first four positive powers of 2.
my_powers = [2**n for n in range(1, 5)]
print(my_powers)    # [2, 4, 8, 16]


# Find all of the number from 1-100 that are divisible by 7
div_by_7 = [x for x in range(101) if x % 7 == 0]
print(div_by_7)    # [0, 7, 14, 21, 28, 35, 42, 49, 56, 63, 70, 77, 84, 91, 98]


# Exercise: Find all of the words in a string that are less than 4 letters.
s = 'the quick brown fox jumped over the lazy dog'
small_words = [word for word in s.split() if len(word) < 4]
print(small_words)  # ['the', 'fox', 'the', 'dog']


# Exercise: Find the sum of all digits of an inputted number
number = "123"
s = sum([int(d) for d in number])
print(s)    # 6


# Tuple comprehensions use parentheses () instead of brackets [].
# Dictionary comprehensions use braces {}.
```

## List Comprehension Exercises

Find all of the numbers from 1-1000 that have a 3 in them.

Count the number of spaces in a string.

Remove all of the vowels in a string.

## Comprehension Challenges

Use a nested list comprehension to find all of the numbers from 1-1000 that are divisible by any single digit besides 1 (2-9)

For all the numbers 1-1000, use a nested list/dictionary comprehension to find the highest single digit by which a number is divisible.

Use a dictionary comprehension to count the length of each word in a sentence.

(We will learn about dictionaries in the next lesson).

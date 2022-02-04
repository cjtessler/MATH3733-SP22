# Exercise Solutions

## 11 Line

``` python
for i in range(5):
    print("#", end="")
print()
```

## 12 Square

``` python
for i in range(5):
    for j in range(5):
        print("#", end="")
    print()
```

## 13 Half of a Square

``` python
# Do NOT delete line 2
n = int(input())

# Write your loops below this line

for i in range(n):
    for j in range(n-i):
        print("#", end ="")
    print()
```

## 14 Sideways Triangle

``` python
w = int(input())

h = 2 * w - 1
for i in range(1, h+1):
    for j in range(w - abs(w-i)):
        print("#", end="")
    print()
```

## 15 Favorite Book

``` python
def favorite_book(title):
    print(f"One of my favorite books is {title}")
```

## 16 Hourglass

``` python
def outer():
    print("#####")

def edge():
    print("#   #")

def almost_middle():
    print(" # # ")

def middle():
    print("  #  ")

def build_hourglass():
    outer()
    edge()
    almost_middle()
    middle()
    almost_middle()
    edge()
    outer()

def build_diamond():
    middle()
    almost_middle()
    almost_middle()
    middle()

## DO NOT CHANGE ANYTHING BELOW THIS LINE
build_hourglass()
print()
build_diamond()
```

## 17 is_even

``` python
def is_even(number):
    if number % 2 == 0:
        return True
    else:
        return False
```

## 18 Quadratic Formula

``` python
import math

def smaller_root(a, b, c):

    disc = b**2 - 4*a*c

    if disc < 0 or a == 0:
        return None

    x = (- b - math.sqrt(disc)) / (2 * a)

    return x
```

## 19 Turtle Drawing

### Instructions

Write a void function (a function that returns `None`) to draw a square. Use it in a program to draw the image shown below. Assume each side is 20 units. 

Hint: Notice that the turtle has already moved away from the ending point of the last square when the program ends.

You might find it useful to review the lesson at [Learn Python the Right Way, Chapter 4](https://learnpythontherightway.com/chapter/chapter-4.html) and the [Official Turtle Documentation](https://docs.python.org/2.7/library/turtle.html) in order to see examples of other methods necessary to recreate the drawing.

![https://learnpythontherightway.com/chapter/Chapter-4/04-04-five_squares.png](https://learnpythontherightway.com/chapter/Chapter-4/04-04-five_squares.png)

### Solution

...

## 20 Recursion

...

## 21 Recursive Turtle

### Instructions

A Sierpinski triangle of order 0 is an equilateral triangle. An order 1 triangle can be drawn by drawing 3 smaller triangles (shown slightly disconnected here, just to help our understanding). Higher order 2 and 3 triangles are also shown. Draw Sierpinski triangles of any order input by the user.

![https://learnpythontherightway.com/chapter/Chapter-18/sierpinski.png](https://learnpythontherightway.com/chapter/Chapter-18/sierpinski.png)

### Solution

...

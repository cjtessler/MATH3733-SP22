# Exercise Solutions

## 01 More on `print()`

``` python
print('''Hello, I'm happy you decided to run this "Python" program!''')
```

## 02 Python as a Calculator

``` python
# Example
# How many seconds are there in 2 minutes, 42 seconds?
print(2 * 60 + 42) # this will print 162

# Exercise 1
# How many seconds are there in 2 hours, 42 minutes, 42 seconds?
print((2 * 60 * 60) + (60 * 42) + 42)

# Exercise 2
# Write an expression that simplifies to 42.0 and 
# uses the exponentiation, addition, subtraction, 
# multiplication, and division operators.
print(2 ** 5 + 11 - (1 / 1 * 1))     # This exercises will be manually checked
```

## 03 Sum of Three Numbers

``` python
a = int(input())
b = int(input())
c = int(input())

print(a + b + c)
```

## 04 Hello!!!!!!!!!!!

``` python
# Obtain name from the user
name = input()

# Obtain a number from the user
num = int(input())

# Print the appropraite output:
print("Hello, " + name + ("!" * num))
```

## 05 Print Digits

``` python
n = input()

tens = int(n) // 10
ones = int(n) % 10

print(tens, ones)
```

## 06 Apple Sharing

``` python
N = int(input())
K = int(input())

print(K // N)
print(K % N)
```

## 07 Parity

``` python
n = int(input())

if n % 2 == 0:
    print("even")
else:
    print("odd")
```

## 08 Sticks and... Triangles

``` python
a = int(input())
b = int(input())
c = int(input())

if a == 0 or b == 0 or c == 0:
    print(False)
elif a > (b + c) or b > (a + c) or c > (a + b):
    print(False)
else: 
    print(True)
```

## 09 Sum of Digits

``` python
# Read an integer:
a = int(input())

total = 0
while a > 0:
    rem = a % 10
    total += rem
    a= a // 10

print(total)
```

## 10 More on `range()`

``` python
for i in range(2, 9, 3):
    print(i, end=" ")
print()
for i in range(20, -6, -5):
    print(i, end=" ")
print()
```

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
n = int(input())

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

``` python
import turtle

# Constants
SQUARE_SIZE = 20
SQUARE_DIST = SQUARE_SIZE + 20
PEN_SIZE = 3
BG_COLOR = "lightgreen"
TURTLE_COLOR = "hotpink"

def draw_square(t):
    # TODO: Complete this function
    for _ in range(4):
        t.forward(20)
        t.left(90)


def main():
    # TODO: Create the turtle
    t = turtle.Turtle()
    t.pensize(PEN_SIZE)
    t.color(TURTLE_COLOR)
    
    # TODO: Change the background color
    turtle.Screen().bgcolor(BG_COLOR)

    # TODO: Draw the squares (Consider a loop)
    for _ in range(5):
        draw_square(t)
        t.penup()
        t.forward(SQUARE_DIST)
        t.pendown()


# DO NOT CHANGE ANYTHING BELOW THIS LINE
if __name__ == "__main__":
    main()
```

## 20 Recursion

``` python
def f(n, a, b):
    if n == 0:
        return 0
    else:
        return a + f(n-1, a + b, b)
```

## 21 Recursive Turtle

### Instructions

A Sierpinski triangle of order 0 is an equilateral triangle. An order 1 triangle can be drawn by drawing 3 smaller triangles (shown slightly disconnected here, just to help our understanding). Higher order 2 and 3 triangles are also shown. Draw Sierpinski triangles of any order input by the user.

![https://learnpythontherightway.com/chapter/Chapter-18/sierpinski.png](https://learnpythontherightway.com/chapter/Chapter-18/sierpinski.png)

### Solution

``` python
def recursive_triangles(t, n, length):  # Added length parameter
    if n == 0:  # Base case
        triangle(t, length)
    else:
        # Draw first triangle at starting position (reduce n by one and length by half)
        recursive_triangles(t, n-1, length / 2)

        # Move to midpoint of bottom side
        t.forward(length/2)

        # Draw second triangle
        recursive_triangles(t, n-1, length / 2)

        # Move back to starting location
        t.bk(length/2)

        # Face alongside left side
        t.left(60)

        # Move to middle of left side
        t.forward(length / 2)

        # Face right to prepare for last triangle
        t.right(60)

        # Draw top triangle
        recursive_triangles(t, n-1, length / 2)

        # Return to starting location
        t.left(60)
        t.back(length / 2)
        t.right(60)

def triangle(t, size):
    for _ in range(3):
        t.forward(size)
        t.left(120.0)
```

## 22 String Slices

``` python
# Read a string:
s = input()

# 1. In the first line, print the third character of this string.
print(s[2])

# 2. In the second line, print the second to last character of this string.
print(s[-2])

# 3. In the third line, print the first five characters of this string.
print(s[:5])

# 4. In the fourth line, print all but the last two characters of this string.
print(s[:-2])

# 5. In the fifth line, print all the characters of this string with even indices (remember indexing starts at 0, so the characters are displayed starting with the first).
print(s[0::2])

# 6. In the sixth line, print all the characters of this string with odd indices (i.e. starting with the second character in the string).
print(s[1::2])

# 7. In the seventh line, print all the characters of the string in reverse order.
print(s[::-1])

# 8. In the eighth line, print every second character of the string in reverse order, starting from the last one.
print(s[::-2])

# 9. In the ninth line, print the length of the given string.
print(len(s))
```

## 23 str.count() methood

``` python
print(s.count(" ") + 1)
```

## 24 Two Halves

``` python
s = input()

l = len(s)

first_half = s[:(l // 2) + 1]

second_half = s[l // 2:]
print(second_half + first_half)
```

## 25 String find methods

``` python
# Read a string:
s = input()

first_occurence = s.find("p")
last_occurence = s.rfind("p")

if first_occurence == -1:
    print(-2)
elif first_occurence == last_occurence:
    print(-1)
else:
    print(s.find("p", first_occurence+1))
```

## 26 str.replace() method

``` python
print(s.replace("1", "one"))
```

## 27 Deleting a Character

``` python
print(s.replace("@", ""))
```

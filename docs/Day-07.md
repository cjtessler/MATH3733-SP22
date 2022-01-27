## Introduction to Turtle Module

[https://www.reddit.com/r/Python/comments/7mo2l8/turtle_module_drawing_a_randomised_landscape/](https://www.reddit.com/r/Python/comments/7mo2l8/turtle_module_drawing_a_randomised_landscape/)

[https://docs.python.org/3/library/turtle.html](https://docs.python.org/3/library/turtle.html)

```python
import turtle

# We create a Turtle object and assign it to a variable named bob
bob = turtle.Turtle()
print(bob)
turtle.mainloop()

# objects have methods, which is just a function attached to an object
bob.forward(100)
bob.left(90)
bob.forward(100)

```

**Exercise:** Modify the program to draw a square.

```python
import turtle

# We create a Turtle object and assign it to a variable named bob
bob = turtle.Turtle()
turtle.mainloop()

# objects have methods, which is just a function attached to an object
bob.forward(100)
bob.left(90)
bob.forward(100)
bob.left(90)
bob.forward(100)
bob.left(90)
bob.forward(100)
bob.left(90)
```

We can do the same thing more concisely with a `for`  loop.

```python
for i in range(4):
	bob.forward(100)
	bob.left(90)
```

Write a function called square that takes a parameter named `t`, which is a turtle.

```python
def square(t):
    '''Draws a square with sides of a given length

    Returns the Turtle to the starting position and location.
    '''
    for i in range(4):
        t.forward(100)
        t.left(90)

square(bob)
# Wrapping a piece of code up in a function is called encapsulation.
# Attaches name to code, which serves as a kind of documentation.
# Allows easy code reuse
# If you ever find yourself copying and pasting, encapsulate the code
```

Add another parameter, named `length`, to square.

Modify the body so the length of the sides is `length`, and then modify the function call to provide a second argument.

Run the program again. Test your program with a range of values for length.

```python
def square(t, length):
    '''Draws a square with sides of a given length

    Returns the Turtle to the starting position and location.
    '''
    for i in range(4):
        t.forward(length)
        t.left(90)

square(bob, 100)
square(bob, 10)
square(bob, 1000)

# Adding a parameter to a function is called generalization
```

Make a copy of `square` and change the name to `polygon`.

Add another parameter named `n` and modify the body so it draws an n-sided regular polygon.

Recall the exterior angles of an n-sided polygon are 360/n degrees.

```python
def polygon(t, n=4, length=10):
    '''Draws a polygon with n sides.
	By default, it draws a square with side length 10.
    t: Turtle object
    n: number of line segments
    length: length (in pixels) of each side
    '''
    angle = 360.0 / n
    for i in range(n):
        t.forward(length)
        t.left(angle)

polygon(bob, n=11, length=100) # n and length are 'keyword arguments'
```
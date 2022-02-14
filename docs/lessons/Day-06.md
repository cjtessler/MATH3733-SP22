---
math: katex
parent: Lessons
---

# Day 06

## Bisection Search

We first use a bisection search to find the $$\sqrt{16}$$.

<img src="../images/06-bisection_example.png" alt="06-bisection_example" style="zoom:50%;" />

In general, we search by taking the midpoint.

<img src="../images/06-bisection_general.png" alt="06-bisection_general" style="zoom: 50%;" />

Here is an implementation of the bisection search.

```python
# Find the square root of a number x
x = int(input(">"))
epsilon = 0.01
low = 0
high = max(1, x)
guess = (high + low) / 2
num_guesses = 1

# Perform bisection search for the square root
while abs(guess ** 2 - x) >= epsilon:
    print(f"low: {low}, high: {high}, guess: {guess}")
    num_guesses += 1
    if guess ** 2 < x:
        low = guess
    else:
        high = guess
    guess = (high + low) / 2

# Outside the while loop
print("Number of guess:", num_guesses)
print(guess, "is close to the square root of x")
```

**Exercise:** Empire State Building is 102 stories high. A man wants to know the highest floor from which he could drop an egg without the egg breaking. He proposed to drop an egg from the top floor, and if it broke, he would go down one floor and try again. At worst, this method would take 102 eggs. In the worst-case scenario (the egg always breaks), how many eggs would be used if he used a bisection search instead?

**Solution:** He would test on the following floors:

- (0+102) // 2 = 51
- (0+51) // 2 = 25 (We use integer division since we cannot have a half floor)
- (0+25) // 2 = 12
- (0+12) // 2 = 6
- (0+6) // 2 = 3
- (0+3) // 2 = 1
- (0 +1) // 2 = 0

He would use 7 eggs. Notice $$\log_2(102) \approx 7$$.

## Functions and Scoping

### Basic Functions

```python
def my_func():
    print("My first function")

my_func()
print(my_func()) # prints None because first_function does 'return' information
```

We will now learn to define our own functions.

### Returning Functions

We can use a docstring to explain what the function does. Talk about code intelligence

```python
# This defines the function
def absolute_value(x):  # x is a formal parameter
    '''Returns the absolute value of the input.'''
    if x < 0:
        return -x
    else:
        return x

absolute_value(-10) # calls the function, but doesn't print its return value
print(absolute_value(-10))
a = absolute_value(-10)
print("The absolute value of -10 is", a)
```

The `x` in the parentheses in the function’s definition is a **formal parameter**.

When the function is called with an argument (-10, above), the argument is assigned to the formal parameter in the function.

As soon as a `return` statement is encountered, the value of the expression following the `return` statement is returned to the caller and no other code is executed in the function.


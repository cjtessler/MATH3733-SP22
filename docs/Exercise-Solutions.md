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

## Quadratic Formula

``` python
import math

def smaller_root(a, b, c):

    disc = b**2 - 4*a*c

    if disc < 0 or a == 0:
        return None

    x = (- b - math.sqrt(disc)) / (2 * a)

    return x
```

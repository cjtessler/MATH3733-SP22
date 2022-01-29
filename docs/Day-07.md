# Day 07

## Modules

A module is a file that contains a collection of related functions.

``` python
>>> import math
>>> math
<module 'math' (built-in)>
>>> dir(math)
['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'copysign', 'cos', 'cosh', 'degrees', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'pi', 'pow', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc']
>>> sin(0)
Traceback (most recent call last):
  File "<pyshell#3>", line 1, in <module>
    sin(0)
NameError: name 'sin' is not defined
>>> math.sin(0)
0.0
>>> math.pi
3.141592653589793
>>> math.sin(math.pi)
1.2246467991473532e-16              # VERY small float
>>> from math import sin, pi        # Removes need for dot notation
>>> pi
3.141592653589793
>>> sin(pi)
1.2246467991473532e-16
>>> 
```

[https://docs.python.org/3/library/math.html](https://docs.python.org/3/library/math.html)

## Exercise 1

Write a function that returns the area of a circle with a given radius.

``` python
import math

def area_of_circle(radius):
    a = math.pi * radius**2
    return a

# The following definition of the function is viable,
# but the use of a "temporary variable" can make debugging easier.
def area_of_circle(radius):
    return math.pi * radius ** 2

print(area_of_circle(4))
```

## Exercise 2

The function `math.sin(x)` returns the sine of `x` radians. Review code intellisense docstring.

Write a function `sin_of_degress(x)` that returns the sine of `x` degrees.

Recall pi radians == 180 degrees.

``` python
from math import sin, pi

def sin_of_degrees(x):
    rad = x * pi / 180 
    result = sin(rad)
    return result

print(sin_of_degrees(180))
```

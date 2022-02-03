# Day 09

One limitation of this solution is that `n` is constant. Large values of `n` yield poor approximations. We do not want to complicate the **interface** by adding more parameters.

Choose an appropriate value of `n` depending on the circumference.

``` python
def circle(t, r):
    ''' Draws an approximated circle.'''
    circumference = 2 * pi * r
    # n = (circumference / 3) + 3 to illustrate preconditions
    n = int(circumference / 3) + 3  # adding three guarentees the polygon has at least 3 sides
    length_per_side = circumference / n
    polygon(t, length_per_side, n)
```

## Exercise 5

Make a more general version of `circle` called `arc` that takes an additional parameter, `angle`, which determines what fraction of the circle to draw.

`angle` is in units of degrees, so when `angle=360`, `arc` should draw a complete circle.

```python
def arc(t, r, angle):
    arc_length = 2 * pi * r * (angle / 360)
    n = int(arc_length / 3) + 1
    step_length = arc_length / n
    step_angle = float(angle) / n
    
    for i in range(n):
        t.forward(step_length)
        t.left(step_angle)
```

We have used the same code in multiple places.

```python
# Refactoring
def polyline(t, n, length, angle):
    for i in range(n):
        t.forward(length)
        t.left(angle)

    
def polygon(t, n, length):
    angle = 360.0 / n
    polyline(t, n, length, angle)
    
    
def arc(t, r, angle):
    arc_length = 2 * math.pi * r * angle / 360
    n = int(arc_length / 3) + 1
    step_length = arc_length / n
    step_angle = float(angle) / n
    polyline(t, n, step_length, step_angle)
 

def circle(t, r):
    arc(t, r, 360)
```

## Functions

Functions are reusable pieces of code.

Functions are not run in a program until they are "called" or "invoked" in a program.

Function characteristics:

- has a **name**
- has **parameters** (0 or more)
- has a **docstring** (optional but recommended)
- has a **body**
- **returns** something (`None` is nothing specified)

Called a function creates a new **scope/frame/environment**.

[Python Tutor - Scope Example 1](https://pythontutor.com/visualize.html#code=def%20f%28x%29%3A%20%23%20name%20x%20used%20as%20formal%20parameter%20%0A%20%20%20%20y%20%3D%201%20%0A%20%20%20%20x%20%3D%20x%20%2B%20y%20%0A%20%20%20%20print%28'x%20%3D',%20x%29%20%0A%20%20%20%20return%20x%20%0A%20%20%20%20%0Ax%20%3D%203%20%0Ay%20%3D%202%20%0Az%20%3D%20f%28x%29%20%23%20value%20of%20x%20used%20as%20actual%20parameter%20%0Aprint%28'z%20%3D',%20z%29%20%0Aprint%28'x%20%3D',%20x%29%20%0Aprint%28'y%20%3D',%20y%29%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)

``` python
def f(x): # name x used as formal parameter 
    y = 1 
    x = x + y 
    print('x =', x) 
    return x 
    
x = 3 
y = 2 
z = f(x) # value of x used as actual parameter 
print('z =', z) 
print('x =', x) 
print('y =', y) 
```

[Python Tutor - Scope Example 2](https://pythontutor.com/visualize.html#code=def%20f%28x%29%3A%20%0A%20%20%20%20def%20g%28%29%3A%20%0A%20%20%20%20%20%20%20%20x%20%3D%20'abc'%20%0A%20%20%20%20%20%20%20%20print%28'x%20%3D',%20x%29%20%0A%0A%20%20%20%20def%20h%28%29%3A%20%0A%20%20%20%20%20%20%20%20z%20%3D%20x%20%0A%20%20%20%20%20%20%20%20print%28'z%20%3D',%20z%29%20%0A%0A%20%20%20%20x%20%3D%20x%20%2B%201%20%0A%20%20%20%20print%28'x%20%3D',%20x%29%20%0A%20%20%20%20h%28%29%20%0A%20%20%20%20g%28%29%20%0A%20%20%20%20print%28'x%20%3D',%20x%29%20%0A%20%20%20%20return%20g%20%0A%0Ax%20%3D%203%20%0Az%20%3D%20f%28x%29%20%0Aprint%28'x%20%3D',%20x%29%20%0Aprint%28'z%20%3D',%20z%29%20%0Az%28%29%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)

``` python
def f(x): 
    def g(): 
        x = 'abc' 
        print('x =', x) 

    def h(): 
        z = x 
        print('z =', z) 

    x = x + 1 
    print('x =', x) 
    h() 
    g() 
    print('x =', x) 
    return g 

x = 3 
z = f(x) 
print('x =', x) 
print('z =', z) 
z() 
```

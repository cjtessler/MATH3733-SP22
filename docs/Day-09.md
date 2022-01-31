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

### Exercise 5

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
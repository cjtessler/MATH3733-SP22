
---
parent: Lessons
---

# Day 16: Dictionaries and Memoization

## Dictionaries

[https://docs.python.org/3.8/tutorial/datastructures.html#dictionaries](https://docs.python.org/3.8/tutorial/datastructures.html#dictionaries)

### Dictionary Syntax

``` python
##### Dictionaries #####
# A dictionary is more general than a list.
# A list's elements were accessed using integer indices.
# A dictionary's elements are accessed by using key.

# Initialize an empty dictionary
eng2sp = dict()     # This one has some other advantages (see documentation)
eng2sp = {}
print(eng2sp)

# Add elements to a dictionary
eng2sp['one'] = 'uno'
print(eng2sp)

eng2sp['two'] = 'dos'
print(eng2sp)

# New in Python 3.6 Dictionaries are ordered in the way you add items.
eng2sp['three'] = 'tres'

# Create/Update a dictionary
# Syntax: {key: value, ...}
eng2sp = {'one': 'uno', 'two': 'dos', 'three': 'tres'}
# eng2sp = {            Alternative declartion for readability
#     'one': 'uno',
#     'two': 'dos',
#     'three': 'tres'
# }

print(eng2sp)

# Access elements in a dictionary
print(eng2sp['two'])
print(eng2sp['four']) # KeyError
```

### Iterating through Dictionaries

``` python
### Iterate through a dictionary
# Looks at keys by default
for entry in eng2sp:
    print(entry) 

for key in eng2sp.keys():
    print(key)

print('one' in eng2sp)  # True
print('uno' in eng2sp)  # False

# Iterate through values
for value in eng2sp.values():
    print(value)

# Iterate through key and values
for key, val in eng2sp.items():
    print(key, val)
```

### Dictionaries as a Collection of Counter

``` python
### Dictionaries as a collection of counters
# Suppose you are given a string and want to count how many times each letter appears.
def histogram(s):
    d = {}
    for c in s:
        if c not in d:
            # create the key is not present
            d[c] = 1
        else:
            # increment the value if k is present
            d[c] += 1
    return d

def histogram(s):
    d = {}
    for c in s:
        d[c] = d.get(c, 0) + 1
    return d

h = histogram('parrot')
print(h)    # {"p": 1, "a": 1, "r": 2, "o": 1, "t": 1}
```

## Passing by reference

[Python Tutor - Passing by Reference](https://pythontutor.com/visualize.html#code=a%20%3D%20%5B1,%202,%203%5D%0A%0Adef%20f%28lst%29%3A%0A%20%20%20%20lst.append%284%29%0A%0Af%28a%29%0A%0Aprint%28a%29&cumulative=false&curInstr=7&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)

## Memoization

``` python
# Fibonacci Revisited
def fib(n):
    if n == 1 or n == 2:
        return 1
    else:
        return fib(n-1) + fib(n-2)

memo = {
    1: 1, 
    2: 1
}

def fib_memo(n: int, memo: dict) -> int:
    if n in memo:
        return memo[n]
    else:
        memo[n] = fib_memo(n-1, memo) + fib_memo(n-2, memo)
        return memo[n]


from time import time
n = 35

start = time()
print(fib(n))
end = time()
print(f"fib({n}) took {end-start} seconds")         # 3.393 seconds

start = time()
print(memo_fib(n, memo))
end = time()
print(f"memo_fib({n}) took {end-start} seconds")    # 0.000038 seconds
```

[Fibonacci Memoization Tree](https://youtu.be/oBt53YbR9Kk?t=1913)

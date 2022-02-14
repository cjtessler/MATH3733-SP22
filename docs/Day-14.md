# Day 15

## Lists

``` python
##### Lists #####
# Lists are used to store multipe items in a single variable.

### Grades...
## ...with variables
t1 = 100
t2 = 90
t3 = 70.5

## ...with lists
grades = [100, 90, 80]
print(grades)
print(grades[0])
print(grades[1:2])

### Add grades to the list
## Operations
grades = grades + [70, 60, 50] # concatenates list
print(grades)   # [100, 90, 80, 70, 60, 50]
grades *= 2     # concatenates a copy of the current list to the end
print(grades)   # [100, 90, 80, 70, 60, 50, 100, 90, 80, 70, 60, 50]

## Append Method
grades = [100, 80, 70]
grades.append(42)
print(grades)   # [100, 80, 70, 42]

grades[1] = 100	# list are mutable
print(grades)   # [100, 100, 80, 42]

## Wrong ways...
grades = grades.append(42)  # deletes current grade list
grades + [42]               # does not save new item
grades = grades + 42        # list concatenation requires two lists


### Iterating over a list
for grade in grades:
    print(grades)

### Exercise: Write a program that counts the number of A's, B's, C's, and failures in a list of grades. Use a 10-point scale.

# generates random list of 30 grades
from random import randrange

grades = []
for i in range(30):
    grades.append(randrange(100))
print(grades)

# create counter variables
a = 0
b = 0
c = 0
fail = 0

# start iterating through list
# check in which range each grade lies
# and add to appropriate counter
for grade in grades:
    if grade > 90:
        a += 1
    elif 80 < grade <= 90:
        b += 1
    elif 70 < grade <= 80:
        c += 1
    else:
        fail += 1

# output
print ("A's: ", a)
print ("B's: ", b)
print ("C's: ", c)
print ("Fails: ", fail)

### Use indexing when modifying elements
## Taxes
prices = [0.99, 14.95, 7.00]

# Undesired behavior
for p in prices: # makes a 'copy' of each element and stores it in p
    p *= 1.07
   
# notice prices haven't changed
print(prices) 	# [0.99, 14.95, 7.00]

# Correct: use indexing to modify original list (if absolutely necessary)
for index in range(len(prices)):
    prices[index] *= 1.07

print(prices)   # [1.0593000000000001, 15.996500000000001, 7.49]

### Searching
my_grocery_list = ['milk', 'cake', 'pizza']
if 'cake' in my_grocery:
    print('yum!')
else:
    print('nope')

    
### Exercise: Given these two lists, write a program that finds all elements that exist in both lists (i.e. the integer 2 exists in both lists). Store your results in a new list and print it out to the user. The expected answer is: [1, 2, 3]

a = [1,2,3,4,5]
b = [2,3,10,11,12,1]

c = []
for element in a:
    if element in b:
        c.append(element)
        # c += [element] alternatively
    
print(c)    # [1, 2, 3]
```

## Methods

``` python
c = [1, 2, 3]

# Remove a specific item
mylist = c[:] # makes a copy of c called mylist
mtlist.remove(1)
print(mylist)
print(c)

# Aliasing
# The association of a variable with an object is called a reference.
# In this example there are two references to the same object
aliaslist = c # make an alias for c called aliaslist
aliaslist.remove(1)
print(c)

# Trying to remove an element that is not in the list raises an error
c.remove(4) # Error
if 4 in c:
    c.remove(4)
 
# Removing an item by index
del c[0]	# del is an operator
print(c)

# Remove and store the item in a variable using the pop method
value_at_zero = c.pop(0)
print(c)
print(value_at_zero)

### Ordering a list
mylist = [9, 3, 11]
mylist.sort() # modifies original list

mylist = [9, 3, 11]
print(sorted(mylist))   # returns a copy that is sorted
print(mylist)           # sorted() does not modify original list

mylist.reverse()        # modifies original list
print(mylist)

### Other methods
mylist = [9, 3, 11]

# index
print(mylist.index(3))  # 1
print(mylist.index(5))  # ValueError
x = 3
if x in mylist:
    print(x, "is at index", mylist.index(x))
    
# extrema
print(min(mylist))
print(max(mylist))

# split
text = input('Enter some text: ')
text.split()
print(text)
print('You entered', len(text), 'words.')

scores = '90,67,87,102,77,80'
scores = scores.split(',')
print(scores)

# list()
# Requires an object you can iterate over (iterable).
print(list(range(100)))
print(list('hello'))
print(list(42)) # TypeError: 'int' object is not iterable


### Exercise: Grocery List Input
# Adds grocery items to a list as they are input, until the user enters "done".
# Prints the sorted list

def main():
    # initialize empty list
    grocery_list = [] 

    # adds items to list
    while item != 'done':
        item = input('Enter a grocery item or "done": ')
        grocery_list.append(item) # add to list

    # organize list alphabetically
    grocery_list.sort() 

    print()
    
    for item in grocery_list:
        print(item)

main()

### Write a function that receives a list of integers and returns their sum.
def sum_list(mylist):
    total = 0
    for i in mylist:
        total += i
    return total

print(sum_list([1, 2, 3]))  # user-defined
print(sum[1, 2, 3])         # built-in


### Nested Lists
matrix = [[1, 2, 3],
         [4, 5, 6],
         [7, 8, 9]]

print(matrix[1][1])
```

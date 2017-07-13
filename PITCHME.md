
## Python Numbers, Type Conversion and Mathematics
<br>

---
<br>
<h4><span style="color:black">python numbers</span></strong></h4>
<h4><span style="color:black">Python list</span></strong></h4>
<h4><span style="color:black">python tuples</span></strong></h4>
<h4><span style="color:black">Python string</span></strong></h4>
<h4><span style="color:black">Python set</span></strong></h4>
<h4><span style="color:black">Python Dictionary</span></strong></h4>

---
Python supports integers, floating point numbers and complex numbers. They are defined as <i>int</i>, <i>float</i> and <i>complex</i> class in Python.

Integers and floating points are separated by the presence or absence of a decimal point. 5 is integer whereas 5.0 is a floating point number.
---

Complex numbers are written in the form, <i>x + yj</i>, where <i>x</i> is the real part and <i>y</i> is the imaginary part.

We can use the <i>type()</i> function to know which class a variable or a value belongs to and is <i>instance()</i> function to check if it belongs to a particular class.

---

```python
a = 5

# Output: <class 'int'>
print(type(a))

# Output: <class 'float'>
print(type(5.0))

# Output: (8+3j)
c = 5 + 3j
print(c + 3)

# Output: True
print(isinstance(c, complex))
```
---
While integers can be of any length, a floating point number is accurate only up to 15 decimal places (the 16th place is inaccurate).

Numbers we deal with everyday are decimal (base 10) number system. But computer programmers (generally embedded programmer) need to work with binary (base 2), hexadecimal (base 16) and octal (base 8) number systems.
---

In Python, we can represent these numbers by appropriately placing a prefix before that number. Following table lists these prefix.


####Number system prefix for Python numbers
Number System |  Prefix
------------ | -------------
Binary |'0b' or '0B'
Octal | '0o' or '0O'
Hexadecimal | '0x' or '0X'
---
###Examples
```python
# Output: 107
print(0b1101011)

# Output: 253 (251 + 2)
print(0xFB + 0b10)

# Output: 13
print(0o15)
```
---
Type Conversion
We can convert one type of number into another. This is also known as coercion.

Operations like addition, subtraction coerce integer to float implicitly (automatically), if one of the operand is float.
```python
>>> 1 + 2.0
3.0
```
We can see above that 1 (integer) is coerced into 1.0 (float) for addition and the result is also a floating point number.
---
We can also use built-in functions like int(), float() and complex() to convert between types explicitly. These function can even convert from strings.

```python
>>> int(2.3)
2
>>> int(-2.8)
-2
>>> float(5)
5.0
>>> complex('3+5j')
(3+5j)
```
When converting from float to integer, the number gets truncated (integer that is closer to zero).
Python Decimal
Python built-in class float performs some calculations that might amaze us. We all know that the sum of 1.1 and 2.2 is 3.3, but Python seems to disagree.
---
```python
>>> (1.1 + 2.2) == 3.3
False
```
---
What is going on?

It turns out that floating-point numbers are implemented in computer hardware as binary fractions, as computer only understands binary (0 and 1). Due to this reason, most of the decimal fractions we know, cannot be accurately stored in our computer.

Let's take an example. We cannot represent the fraction 1/3 as a decimal number. This will give 0.33333333... which is infinitely long, and we can only approximate it.

Turns out decimal fraction 0.1 will result into an infinitely long binary fraction of 0.000110011001100110011... and our computer only stores a finite number of it.

This will only approximate 0.1 but never be equal. Hence, it is the limitation of our computer hardware and not an error in Python.
---
```python
>>> 1.1 + 2.2
3.3000000000000003
```
To overcome this issue, we can use decimal module that comes with Python. While floating point numbers have precision up to 15 decimal places, the decimal module has user settable precision.
```python
import decimal

# Output: 0.1
print(0.1)

# Output: Decimal('0.1000000000000000055511151231257827021181583404541015625')
print(decimal.Decimal(0.1))
```
---
When to use Decimal instead of float?
We generally use Decimal in the following cases.

When we are making financial applications that need exact decimal representation.
When we want to control the level of precision required.
When we want to implement the notion of significant decimal places.
When we want the operations to be carried out like we did at school
Python Fractions
Python provides operations involving fractional numbers through its fractions module.
---
A fraction has a numerator and a denominator, both of which are integers. This module has support for rational number arithmetic.

We can create Fraction objects in various ways.
```python
import fractions

# Output: 3/2
print(fractions.Fraction(1.5))

# Output: 5
print(fractions.Fraction(5))

# Output: 1/3
print(fractions.Fraction(1,3))
```
----
While creating Fraction from float, we might get some unusual results. This is due to the imperfect binary floating point number representation as discussed in the previous section.

Fortunately, Fraction allows us to instantiate with string as well. This is the preferred options when using decimal numbers.
```python
import fractions

# As float
# Output: 2476979795053773/2251799813685248
print(fractions.Fraction(1.1))

# As string
# Output: 11/10
print(fractions.Fraction('1.1'))
```
---

This datatype supports all basic operations. Here are few examples.

```python
from fractions import Fraction as F

# Output: 2/3
print(F(1,3) + F(1,3))

# Output: 6/5
print(1 / F(5,6))

# Output: False
print(F(-3,10) > 0)

# Output: True
print(F(-3,10) < 0)
```
---
###Python Mathematics
---
Python offers modules like math and random to carry out different mathematics like trigonometry, logarithms, probability and statistics, etc.
```python
import math

# Output: 3.141592653589793
print(math.pi)

# Output: -1.0
print(math.cos(math.pi))

# Output: 22026.465794806718
print(math.exp(10))

# Output: 3.0
print(math.log10(1000))

# Output: 1.1752011936438014
print(math.sinh(1))

# Output: 720
print(math.factorial(6))
```
---

```python
import random

# Output: 16
print(random.randrange(10,20))

x = ['a', 'b', 'c', 'd', 'e']

# Get random choice
print(random.choice(x))

# Shuffle x
random.shuffle(x)

# Print the shuffled x
print(x)

# Print random element
print(random.random())
```
---
###Python List.
---
Python offers a range of compound datatypes often referred to as sequences. List is one of the most frequently used and very versatile datatype used in Python.


####How to create a list?
In Python programming, a list is created by placing all the items (elements) inside a square bracket [ ], separated by commas.

It can have any number of items and they may be of different types (integer, float, string etc.).

```python
# empty list
my_list = []

# list of integers
my_list = [1, 2, 3]

# list with mixed datatypes
my_list = [1, "Hello", 3.4]

```

Also, a list can even have another list as an item. This is called nested list.
```python
# nested list
my_list = ["mouse", [8, 4, 6], ['a']]
```
---

###How to access elements from a list?
There are various ways in which we can access the elements of a list.

####List Index
We can use the index operator [] to access an item in a list. Index starts from 0. So, a list having 5 elements will have index from 0 to 4.

Trying to access an element other that this will raise an IndexError. The index must be an integer. We can't use float or other types, this will result into TypeError.

Nested list are accessed using nested indexing.
---
###List Index
We can use the index operator [] to access an item in a list. Index starts from 0. So, a list having 5 elements will have index from 0 to 4.
Trying to access an element other that this will raise an IndexError. The index must be an integer. We can't use float or other types, this will result into TypeError.
Nested list are accessed using nested indexing.
---
```python
my_list = ['p','r','o','b','e']
# Output: p
print(my_list[0])

# Output: o
print(my_list[2])

# Output: e
print(my_list[4])

# Error! Only integer can be used for indexing
# my_list[4.0]

# Nested List
n_list = ["Happy", [2,0,1,5]]

# Nested indexing

# Output: a
print(n_list[0][1])    

# Output: 5
print(n_list[1][3])
```
---
###Negative indexing
Python allows negative indexing for its sequences. The index of -1 refers to the last item, -2 to the second last item and so on.
```python
my_list = ['p','r','o','b','e']

# Output: e
print(my_list[-1])

# Output: p
print(my_list[-5])
```
---
###How to slice lists in Python?

We can access a range of items in a list by using the slicing operator (colon).

```python
my_list = ['p','r','o','g','r','a','m','i','z']
# elements 3rd to 5th
print(my_list[2:5])

# elements beginning to 4th
print(my_list[:-5])

# elements 6th to end
print(my_list[5:])

# elements beginning to end
print(my_list[:])
```
---
Slicing can be best visualized by considering the index to be between the elements as shown below. So if we want to access a range, we need two index that will slice that portion from the list.

![PROGRAMIZ](https://cdn.programiz.com/sites/tutorial2program/files/element-slicling.jpg)

###How to change or add elements to a list?
List are mutable, meaning, their elements can be changed unlike string or tuple.

We can use assignment operator (=) to change an item or a range of items.
```python
# mistake values
odd = [2, 4, 6, 8]

# change the 1st item    
odd[0] = 1            

# Output: [1, 4, 6, 8]
print(odd)

# change 2nd to 4th items
odd[1:4] = [3, 5, 7]  

# Output: [1, 3, 5, 7]
print(odd)                   
```
---

We can add one item to a list using append() method or add several items using extend() method.

```python
odd = [1, 3, 5]

odd.append(7)

# Output: [1, 3, 5, 7]
print(odd)

odd.extend([9, 11, 13])

# Output: [1, 3, 5, 7, 9, 11, 13]
print(odd)
```
---
We can also use + operator to combine two lists. This is also called concatenation.

The * operator repeats a list for the given number of times.
```python
odd = [1, 3, 5]

# Output: [1, 3, 5, 9, 7, 5]
print(odd + [9, 7, 5])

#Output: ["re", "re", "re"]
print(["re"] * 3)
```
---
Furthermore, we can insert one item at a desired location by using the method insert() or insert multiple items by squeezing it into an empty slice of a list.
```python
odd = [1, 9]
odd.insert(1,3)

# Output: [1, 3, 9] 
print(odd)

odd[2:2] = [5, 7]

# Output: [1, 3, 5, 7, 9]
print(odd)
```
---
###How to delete or remove elements from a list?
We can delete one or more items from a list using the keyword del. It can even delete the list entirely.
my_list = ['p','r','o','b','l','e','m']
```python
# delete one item
del my_list[2]

# Output: ['p', 'r', 'b', 'l', 'e', 'm']     
print(my_list)

# delete multiple items
del my_list[1:5]  

# Output: ['p', 'm']
print(my_list)

# delete entire list
del my_list       

# Error: List not defined
print(my_list)
```
---
We can use remove() method to remove the given item or pop() method to remove an item at the given index.

The pop() method removes and returns the last item if index is not provided. This helps us implement lists as stacks (first in, last out data structure).

We can also use the clear() method to empty a list.
```python

my_list = ['p','r','o','b','l','e','m']
my_list.remove('p')

# Output: ['r', 'o', 'b', 'l', 'e', 'm']
print(my_list)

# Output: 'o'
print(my_list.pop(1))

# Output: ['r', 'b', 'l', 'e', 'm']
print(my_list)

# Output: 'm'
print(my_list.pop())

# Output: ['r', 'b', 'l', 'e']
print(my_list)

my_list.clear()

# Output: []
print(my_list)
```
---
Finally, we can also delete items in a list by assigning an empty list to a slice of elements.
```python
>>> my_list = ['p','r','o','b','l','e','m']
>>> my_list[2:3] = []
>>> my_list
['p', 'r', 'b', 'l', 'e', 'm']
>>> my_list[2:5] = []
>>> my_list
['p', 'r', 'm']
```
---
###Python List Methods
Methods that are available with list object in Python programming are tabulated below.

They are accessed as list.method(). Some of the methods have already been used above.


###Python List Methods
append() -  Add an element to the end of the list
extend() -  Add all elements of a list to the another list
insert() -  Insert an item at the defined index
remove() -  Removes an item from the list
pop() -     Removes and returns an element at the given index
clear() -   Removes all items from the list
index() -   Returns the index of the first matched item
count() -   Returns the count of number of items passed as an argument
sort() -    Sort items in a list in ascending order
reverse() - Reverse the order of items in the list
copy() -    Returns a shallow copy of the list

Some examples of Python list methods:
```python
my_list = [3, 8, 1, 6, 0, 8, 4]

# Output: 1
print(my_list.index(8))

# Output: 2
print(my_list.count(8))

my_list.sort()

# Output: [0, 1, 3, 4, 6, 8, 8]
print(my_list)

my_list.reverse()

# Output: [8, 8, 6, 4, 3, 1, 0]
print(my_list)
```
---
###Another way to create new List
List comprehension is an elegant and concise way to create new list from an existing list in Python.

List comprehension consists of an expression followed by for statement inside square brackets.

Here is an example to make a list with each item being increasing power of 2.
```python
pow2 = [2 ** x for x in range(10)]

# Output: [1, 2, 4, 8, 16, 32, 64, 128, 256, 512]
print(pow2)
```
---
###Other List Operations in Python

####List Membership Test
We can test if an item exists in a list or not, using the keyword in.
```python

my_list = ['p','r','o','b','l','e','m']

# Output: True
print('p' in my_list)

# Output: False
print('a' in my_list)

# Output: True
print('c' not in my_list)
```
###Iterating Through a List
Using a for loop we can iterate though each item in a list.
```python
for fruit in ['apple','banana','mango']:
    print("I like",fruit)
```
###Built-in Functions with List
Built-in functions like all(), any(), enumerate(), len(), max(), min(), list(), sorted() etc. are commonly used with list to perform different tasks.

Built-in Functions with List
Function	Description
all()	Return True if all elements of the list are true (or if the list is empty).
any()	Return True if any element of the list is true. If the list is empty, return False.
enumerate()	Return an enumerate object. It contains the index and value of all the items of list as a tuple.
len()	Return the length (the number of items) in the list.
list()	Convert an iterable (tuple, string, set, dictionary) to a list.
max()	Return the largest item in the list.
min()	Return the smallest item in the list
sorted()	Return a new sorted list (does not sort the list itself).
sum()	Return the sum of all elements in the list.

###Python Tuple















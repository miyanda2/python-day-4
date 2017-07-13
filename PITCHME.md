
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
Number System | Prefix
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

We can also use built-in functions like int(), float() and complex() to convert between types explicitly. These function can even convert from strings.
---
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










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
<br>

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

In Python, we can represent these numbers by appropriately placing a prefix before that number. Following table lists these prefix.

---
####Number system prefix for Python numbers
Number System | Prefix
------------ | -------------
Binary |'0b' or '0B'
Octal | '0o' or '0O'
Hexadecimal | '0x' or '0X'






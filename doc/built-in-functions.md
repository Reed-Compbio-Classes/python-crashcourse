---
title: Built-in-Functions
layout: default
nav_order: 4
---

### Built-in Functions

A **function** is an executable block of code.  Each function has a name followed by parentheses which may contain zero or more inputs, or **arguments**.  Functions may return values as well.  

| Description  | Name | Num of Arguments | Returns | Examples |
| --- | --- | --- | --- | --- |
| Get the type of an object  | `type()`  | one | the object's type | `type(1.0)` <br> `type('a string')` |
| Print the arguments to the screen | `print()`  | zero or more | nothing | `print()` <br> `print(145.99)` <br> `print('a',1,'b')` |
| Get the length of a list | `len()` | one `list` or `str` | an `int` | `len([1,2,3,4,5])` |
| Get a range of integers | `range()` | one `int` | a `range` object from 0 up to _but not including_ the argument | `range(10)` <br> `range(5)` |
| Convert to a list | `list()` | one | a `list` of the argument | `list(range(5))` |
| Convert to a string | `str()` | one | a `str` of the argument | `str(5)` <br> `str([1,2])` |
| Convert to a float | `int()` | one numeric or `str` | a `float` of the argument | `float('5.0')` <br> `float(5)` |
| Convert to an integer | `int()` | one numeric or `str`| an `int` of the argument | `int(5.0)` <br> `int('5')` |

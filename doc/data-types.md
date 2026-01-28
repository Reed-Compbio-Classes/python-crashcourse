---
title: Data Types
layout: default
nav_order: 3
---

### Numerical Data Types

There are two types of numbers we will work with:
* An **integer** (`int`) is a data type that represents a number with no fractional component (a whole number).
* A **floating point real value** (`float`) is a data type that represents a number with fractional values.

You can check the type of a values with the `type()` function:

```
type(4)
type(4.0)
type(4.000)
type(4.300)
```

This may seem unintuitive - isn't 4 the same as 4.0?  This difference is a result of how Python stores these data types in memory, and beyond the scope of this class.  

### The String Data Type

A **string** (`str`) is a data type that represents a sequence of characters (text).  Like numbers, strings are just another type of data.  Strings are surrounded by quotes, which can be single (e.g., `'hi'`) or double (e.g., `"hi"`).  They can be used in expressions or assignments.

```
'a'
'ab'
stringVar='!'
```

The `+` operator **concatenates strings**.

```
'a'+'b'
'b'+'a'
```

See also [Manipulating Strings](string-manipulation.md) for built-in functions to work with strings.

### The List Data Type

A **list** is an ordered collection of items.  Lists are written as comma-separated expressions surrounded by square brackets. The expressions within a list can be of different types.

```
[5,10,15]
myList = [5,10,15]
stringList = ['hi','there','class']
mixedList = [1,'2','three',4]
```

Each element of a list is assigned a number - its position or **index**. To retrieve the `i`th element of a list (such as a list stored in the `myList` variable), use the expression

```
myList[i]
```

where `i` is an integer.  Watch out: **the index starts at 0!** That is, the first element of `myList` is specified by `myList[0]`.


### The Boolean Data Type and Boolean Expressions

A **boolean** is a data type that can only be one of two values: `True` or `False`.  Booleans can appear as outputs or inputs of some expressions (including some new operators).

| Operator  | Symbol | Input Types | Return Types | Examples |
| --- | --- | --- | --- | --- |
Equality | `==` | numeric or `str` | `boolean` | `1==2` <br> `'a'=='a'` |
Inequality | `!=` | numeric or `str` | `boolean` | `1!=2` <br> `'a'!='a'` |
Less Than  | `<` | numeric | `boolean` | `1<2`<br> `2.0<1.5` |
Less Than<br>or Equal To | `<=`  | numeric | `boolean` | `1<=1`<br> `2.0<=1.5` |
Greater Than | `>`  | numeric | `boolean` | `1>2`<br> `2.0>1.5` |
Greater Than<br>or Equal To | `>=`  | numeric | `boolean` | `1>=1`<br> `2.0>=1.5` |
And | `and` | `boolean` | `boolean` | `True and False`<br>`4>5 and 6>=6` |
Or | `or` | `boolean` | `boolean` | `True or False`<br>`4>=5 or 6>=6` |
Not | `not` | `boolean` | `boolean` | `not True`<br>`not 4<5` |
In | `in` | mixed types | `boolean` | `'a' in ['a','b','c']`<br>`1 in [0,'a',2]` |
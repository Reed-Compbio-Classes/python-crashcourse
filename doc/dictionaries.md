
---
title: Dictionariees
layout: default
nav_order: 9
---

### Dictionaries

Suppose we have a string from a file and we want to count the number of times each word appears:

```
myStr = 'that sam I am that sam I am I do not like that sam I am'
myList = myStr.split()
```

Using what we've learned about so far, it would be straightforward to count the number of times the word `that` appears, but what about counting _all_ occurrences of _all_ words?  

Luckily there's a new type called a **dictionary** that will allow us to complete this task.  A dictionary stores key-value pairs, where the values can be quickly retrieved by keys.
- Keys can be `str`, `int`, `float`, or a mix of types (e.g. some keys can be `str` and others can be `int`)
- Values can be `str`, `int`, `float`, `list`, `Boolean`, `File` (almost anything)

A dictionary is specified by curly braces `{}`. Like initializing an empty list with `[]` you can initialize an empty dictionary:

```
freq = {}
```

You can then add key-value pairs to this dictionary like so:

```
freq['that'] = 3
freq['sam'] = 3
freq['like'] = 1
```

In this example, the keys are `str` and the values are `int`. You can retrieve a value using the key (this will be an **expression**):

```
freq['like']
sam_val = freq['sam']  # assign the value of 'sam' to sam_val
```

You can also assign a new value to a key:

```
freq['sam'] = 100
freq['that'] = freq['that'] + 1
```

Dictionaries also provide some built-in functions to get an iterator of the keys or the values for a dictionary.  You need to explicitly tell Python that these are lists if you want to work with them.

```
for key in freq.keys():
  print(key)

key_list = list(freq.keys())
value_list = list(freq.values())
```

Note if you have the key you can always retrieve the value using `freq[key]`.  

| Description  | Name | Num of Arguments | Returns | Examples |
| --- | --- | --- | --- | --- |
| Get the keys in a dictionary | `keys()`  | zero | `PyListObject` (use `list()` <br> to convert to a list) | `freq.keys()` |
| Get the values in a dictionary | `values()`  | zero | `PyListObject` (use `list()` <br> to convert to a list) | `freq.values()` |
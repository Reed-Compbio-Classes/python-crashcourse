---
title: Manipulating Strings
layout: default
nav_order: 11
---

### Manipulating Strings

When you read in a file, you may want to process the strings in some way.  Luckily, there are functions to easily strip whitespace and split a string into multiple parts.  Strings are types that also have this **special syntax** where functions can be called directly on them.
- To remove any whitespace (including newlines, spaces, and tabs), use the `strip()` function.
- To split a string into multiple parts, use the `split()` function. The `split()` function requires a **delimiter** - a string that will be used to split the string on.  With no arguments, `split()` will use whitespace as a delimiter.  However, you can pass in _any_ string as a delimiter.
- Conversely, you can take a list of strings and concatenate them with a delimiter using the `join()` function.
- You can also replace some text in a string (a _substring_) with another substring with the `replace()` function. The function takes two arguments, and all instances of the first argument are replaced by the second argument.
- Finally, you can also convert all letters to upper-case with `upper()` and all letters to lower-case with `lower()`.  


| Description  | Name | Num of Arguments | Returns | Examples |
| --- | --- | --- | --- | --- |
| Remove <br> whitespace | `strip()`  | zero | `str` | `' abcd   '.strip()` <br> `'abcd\n'.strip()` <br> `myStr.strip()` |
| Split a string on whitespace | `split()`  | zero | `list` of strings | `'my string'.split()` |
| Split a string using <br> a delimiter | `split()` | one `str` | `list` of strings | `'bacad'.split('a')` <br> `myStr.split('-')` <br> `'a\nb\nc\nd\n'.split('\n')` |
| Concatenate a list | `join()` | zero | `str` | `['a','b','c'].join()`  |
| Concatenate a list <br> using a delimiter | `join()` | one `str` | `str` | `['b','c','d'].join('a')`  |
| Replace text in a string | `replace()` | two `str` | `str` | `'new*str'.replace('*',' ')`  |
| Convert letters to uppercase | `upper()` | zero | `str` | `'abc'.upper()` |
| Convert letters to lowercase | `lower()` | zero | `str` | `'ABC'.lower()` |
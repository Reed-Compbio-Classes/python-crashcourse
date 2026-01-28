---
title: User-Defined Functions
layout: default
nav_order: 5
---

### User-Defined Functions

Like built-in functions, user-defined functions have a name followed by parentheses which may contain zero or more inputs, or **arguments**.  Built-in functions may return values as well.  Defining functions in your code has a special syntax:

```
def sing():
  print(‘Happy birthday to you,’)
  print(‘Happy birthday to you,’)
  print(‘Happy birthday dear Teeny,’)
  print(‘Happy birthday to you!’)
  return
```
Let's break this function down:
- The function above is named `sing`, takes zero inputs, and returns nothing.  
- The `def` and colon (`:`) are part of every function definition.
- The **indentation** of the subsequent lines matter -- all lines that are indented under the `def` line will be executed when the function is called.
- The `return` statement at the end denotes that the function is over and, if anything is specified, it will be returned. In this case, the `sing` function returns nothing.

If we enter this in the text editor and hit Run, nothing would be printed! That's because, while we have **defined** our function, we haven't yet **called** it.  That is, we need to explicitly evaluate it:

```
sing()
```

This must happen _after_ the function is defined.
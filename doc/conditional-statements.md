---
title: IF Statements
layout: default
nav_order: 8
---

### Conditional Statements

An **IF** statement specifies a block of code only if some condition (e.g. a Boolean expression) is `True`.  It allows us to say "if some value is `True`, do somthing."  IF statements have a special syntax:

```
x = 4
y = 10
if x < y:
   print('x is less than y')
```
Let's break down the previous lines:
- The first two lines assign integers to variables `x` and `y`.
- The `if` and the colon (`:`) are part of every IF statement.
- There is a Boolean expression (`x < y`), which will evaluate to `True` or `False`.  
 - If the expression evaluates to `True`, then the indented line will be executed.
 - If the expression evaluates to `False`, then the indented line will _not_ be executed.
- Here, the Boolean expression evaluates to `True`, so the string is printed to the scren.  
- Again, the **indentation** in the lines underneath the IF statement matters.

There are variants of this IF statement that allows us to say "if some value is `True`, do something. Otherwise, do something else."  This is called an IF/ELSE statement:

```
x = 4
y = 10
if x < y:
   print('x is less than y')
else:
   print('x is greater than y')
```

Here, only one of the two print statements will be executed, depending on whether the Boolean expression evaluates to `True` or `False` (and enters the `else` block of code).  

Finally, there is an ELIF statement, which allows us to say "if some value is `True`, do something. Otherwise...if some _other_ value is `True`, do something. Otherwise...if some _other_ value is `True`, do something.

```
x = 4
y = 10
if x < y:
   print('x is less than y')
elif x == y:
   print('x and y are equal')
else:
   print('x is greater than y')
```

Note that, while there are now three different print statements, only **one** will ever be printed because only one of the IF/ELIF/ELSE conditions can evaluate to `True`.
---
title: WHILE Loops
layout: default
nav_order: 9
---

### WHILE Loops

A **WHILE loop** specifies repeated execution. However, unlike FOR loops, a WHILE loop keeps iteration until a condition is not met.  The syntax for a WHILE loop looks like this:

```
i = 0
while i < 5:
  print(i)
  i = i + 1
```

Let's break down the previous lines.
- The `while` and the colon (`:`) are part of every WHILE loop.
- There is a Boolean expression between the `while` and the colon (remember that this evaluates to `True` or `False`).
- The **indentation** of the last two lines matter - all lines that are indented under the `while` statement are executed until the Boolean expression evaluates to `False`.

The WHILE loop above will print

```
0
1
2
3
4
```

**Warning**: you must ensure that the WHILE loop terminates! That is, there **must** be some point in your code where the Boolean expression evaluates to `False`.  Consider this code:

```
i = 0
while i < 5:
  print(i)
```

Here, we are not incrementing `i` by one each time.  So the WHILE loop will print

```
0
0
0
0
0
...
```

and so on forever.  This is called an **infinite loop**, and they are no good.

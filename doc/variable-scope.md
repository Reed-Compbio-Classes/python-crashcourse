---
title: Variable Scope
layout: default
nav_order: 6
---

### Variable Scope

Consider the following code snippet:

```
def main():
  x = prog1(100)
  y = prog2(5)
  print(x+y)
  return

def prog1(num):
  return num/10

def prog2(num):
  return num+5

main()
```
The `prog1` and `prog2` functions take inputs, or **arguments**.  In these function definitions, the variable name (e.g. `num`) is a **formal parameter** that is assigned the value of the input when the function is called.

The **scope** of a variable is the part of the program where it may be referenced.  Formal parameters (in the function defintions) and other variables assigned within a function only be used within that function.  Functions can communicate information back to the place where it is called by returning values.  Let's walk through the code above as an example.  The first thing Python will do is store these function definitons in memory, skipping over all the contents.

![scope 1](/figs/scope-1.png)

By the time we are at Line 13 (red arrow), Python has stored three functions in memory (`main`, `prog1`, and `prog2`). Further, Python knows that there is one formal parameter for `prog1` and one formal parameter for `prog2`.  Here, they both happen to be called `num`.  

The next step will call the `main` function, which in turn calls `prog1` with `100` as the input value (Line 2).

![scope 2](/figs/scope-2.png)

When we are within the `prog1` function, note that a **new** memory table has been created to store the variables that are defined within this function.  The `prog1` function assigns the input to the formal parameter, and will return a float.  This value will be store in the `main` function as the variable `x` (Line 2), and will move on to calling `prog2`.

![scope 3](/figs/scope-3.png)

We are now about to return the value from `prog2`. Note that there are three tables now: a **global table**, which contains the function names, a `main` table, and a `prog2` table.  We can only refer to variables within the `prog2` table if we are within the `prog2` function.

![scope 4](/figs/scope-4.png)

At the end of the `main` function, there are two variables within the function (we call these **local variables** to differentiate them from the variables and functions in the global frame).  These variables, `x` and `y`, are the only integers that we can refer to within `main`.  

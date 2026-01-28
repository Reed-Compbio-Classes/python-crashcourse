---
title: Expressions & Assignments
layout: default
nav_order: 2
---

### The Python Interpreter

Navigate to the terminal in VSCode, type `python`, and hit the return key. You have now opened the Python interpreter, where you can directly type python code at the prompt (`>>>`) and it will be evaluated. The Python interpreter can be used like a "Calculator" on your laptop.  When you click the equals sign on your calculator, nothing happens.  This is the same thing as hitting Enter in the Python interpreter.  

![prompt](/figs/prompt.png)

To exit out of this interpreter, type `quit()` and hit the return key. You will return to the original prompt in the terminal (that ends with `$`).

### Expressions

An **expression** is an input that Python evaluates and returns as output.  Expressions follow the order of operations you learned in grade school; parentheses can change this order.  When you evaluate expressions in the Python interpreter, the output is spit out to the screen.  When you evaluate expressions in the text editor, you need to tell the program to print the output to the screen with `print()`.

```
4
4+2
4-2
4*2
4/2
4*4+2
4*(4+2)
4**2
4**3
```

As a general rule, inputs and outputs of expressions have the same type (e.g. numeric, string, or list). For example, the expression 1+2 outputs a number, while the expression '1'+'2' outputs a string.  In Python3, expressions that involve a `float` and an `int` will output a `float`.


### Assignments

An **assignment** is an input that Python evaluates and stores in memory.  An assignment always has three parts: a variable name, an equals sign, and an expression.  

```
A1 = 5
X = A1 + 1
Y = X
newVar = X + Y
```

### Printing Expressions and Assignments

When you are writing expressions and assignments in a Python file (a file that ends in `.py`), remember that you have to explicitly tell Python to print the values to the terminal:

```
print(A1)
print(X)
print(Y)
print(newVar)
```

You may also pass multiple expressions into the `print()` function:

```
print(X,Y)
print('The value of newVar is',newVar)
```
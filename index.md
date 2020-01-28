## Jan 29, 2020: Repl.it, Expressions, and Assignments

We use [repl.it](https://repl.it/) for assignments in this course.  There are three panels for any lab or assignment.
- The right pane includes instructions
- The upper left pane is a text editor (you can write multiple lines of code and evaluate them all using the run button).
- The lower left pane is an interpreter, which takes user input and evaluates each line as you enter it.  Python interpreters have a prompt that begins with `>`.  

### Python as a calculator

The Python interpreter can be used like a "Calculator" on your laptop.  When you click the equals sign on your calculator, nothing happens.  This is the same thing as hitting Enter in the Python interpreter.  

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

An **assignment** is an input that Python evaluates and stores in memory.  An assignment always has three parts: a variable name, an equals sign, and an expression.  

```
A1 = 5
X = A1 + 1
Y = X
newVar = X + Y
```

###

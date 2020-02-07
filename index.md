We use [repl.it](https://repl.it/) for assignments in this course.  There are three panels for any lab or assignment.
* The right pane includes instructions
* The upper left pane is a text editor (you can write multiple lines of code and evaluate them all using the run button).
* The lower left pane is an interpreter, which takes user input and evaluates each line as you enter it.  Python interpreters have a prompt that begins with `>`.  

### PythonTutor

If you are writing code and can't quite figure out why Python is doing something _other_ than what you think it should, [PythonTutor](http://pythontutor.com/) is an **excellent** resource.  It allows you to run your code step-by-step, observing what is stored in memory and what is printed to the console.  

![A screenshot of pythontutor](pythontutor.png)

## Week 1

### Expressions and Assignments

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

### Expression Input and Output Types

As a general rule, inputs and outputs of expressions have the same type (e.g. numeric, string, or list). For example, the expression 1+2 outputs a number, while the expression '1'+'2' outputs a string.  In Python3, expressions that involve a `float` and an `int` will output a `float`.

## Week 2

### Built-in Functions

A **function** is an executable block of code.  Each function has a name followed by parentheses which may contain zero or more inputs, or **arguments**.  Functions may return values as well.  

| Description  | Name | Num of Arguments | Returns | Examples |
| --- | --- | --- | --- | --- 
| Get the type of an object  | `type()`  | one  | the object's type | `type(1.0)` <br> `type('a string')` |
| Print the arguments to the screen | `print()`  | zero or more | nothing | `print()` <br> `print(145.99)` <br> `print('a',1,'b')` |
| Get the length of a list | `len()` | one `list` | an `int` | `len([1,2,3,4,5])` | 
| Get a range of integers | `range()` | one `int` | a `range` object from 0 up to _but not including_ the argument | `range(10)` <br> `range(5)` |
| Convert an object to a list | `list()` | one | a `list` of the argument | `list(range(5))` |

### For Loops

A **for loop** specifies repeated execution. It allows us to say "for each element in a list, do something."  For loops have a special syntax:

```
for item in [0,1,2,3]:
  print(item)
```

Let's break down the previous two lines:
- The `for`, `in`, and the colon (`:`) are part of every for loop.
- There is a list (`[0,1,2,3]`) and a variable name (`item`) that we specified - the list can be any list, and the variable name can be any variable name.  
- The **indentation** in the second line matters -- all lines that are indented under the `for` statement are executed at each iteration.  In this case, we will print the value assigned to the `item` variable.

For loops work by assigning the variable name (`item`, in this case) to **each element** of the list and executing the lines of code that are indented under the for loop.  The for loop above will print

```
0
1
2
3
```

which is exactly the same as if we wrote out each line of the for loop:

```
item = 0
print(item)
item = 1
print(item)
item = 2 
print(item)
item = 3
print(item)
```

For loops can execute multiple lines of code at each iteration, and can iterate over lists containing different elements. For example

```
myList = [1,'hey','there']
for loop_var in myList:
  print(loop_var)
  print(loop_var,'again')
```

will print

```
1
1 again
hey
hey again
there
there again
```

---
title: FOR Loops
layout: default
nav_order: 7
---

### FOR Loops

A **FOR loop** specifies repeated execution. It allows us to say "for each element in a list, do something."  For loops have a special syntax:

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



### Working with Tables

When we began to work with motifs, we represented them as a **list of strings**.  It is often useful to consider them as a table, where each string is a row and we can retrieve a character from a certain column.  This allows us to do things like count the number of `A/C/G/T` in a column to build a counts table or a frequency table.

<p align="center">
  <img src="/figs/list-of-strings.png" alt="lists-of-strings"/>
</p>

You can use this "double indexing" for a **lists of lists** as well: the variable below represents a table with four rows and three columns.

```
ListOfLists = [[1,2,3],[2,3,4],[4,5,6],[5,6,7]]
```

To iterate over the _rows_, you can use the following simple FOR loop:

```
for i in range(len(ListOfLists)):
  for j in range(len(ListOfLists[i])):
    print(ListOfLists[i][j])
```

<p align="center">
  <img src="/figs/rows-first.jpg" alt="rows first"/>
</p>

How can we iterate over the _columns_ first?  To do this, we need to assume that *the length of every row is the same* (since we're working with tables, we can make this assumption).  Then, we simply need to swap the two FOR loops, using the first row to determine the number of columns:

```
for j in range(len(ListOfLists[0])):
  for i in range(len(ListOfLists)):
    print(ListOfLists[i][j])
```

<p align="center">
  <img src="/figs/cols-first.jpg" alt="cols first"/>
</p>

Remember to **always** index into the variable with rows (`i`) and then columns (`j`).
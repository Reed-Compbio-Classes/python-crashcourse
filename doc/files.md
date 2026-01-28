---
title: Files
layout: default
nav_order: 10
---

### Files in Python

For many homeworks, the `helper_functions.py` have included a function to read strings from a text file.  In HW 6.5, you will read text from a file _and_ write text to a file.  This may be very useful for final projects.

When you read a book, you need to **open** the book, **read** the text, and **close** the book.  Reading files in Python follows the same structure.  First, a `File` is a new type (like `int`, `str`, `list`...), but has some built-in functions that are designed to work _only_ with `File` variables.  
- Filenames are represented as strings (e.g. `myfile.txt`)
- You can open a file for **reading** (`r`, default) or **writing** (`w`).  If you're opening a file for reading, the file must already exist.  You can read the contents of the file as a single string (`read()`) or as a list of strings, one for each line (`readlines()`).  These functions have a **special syntax**: they require a `File` object.
- When you are done with either reading or writing, **close** the file with the `close()` function (which also has a special syntax).

| Description  | Name | Num of Arguments | Returns | Examples |
| --- | --- | --- | --- | --- |
| Open a `File`  | `open()`  | two `str` | `File` | `open('myfile.txt','r')` <br> `open('myfile.txt','w')` |
| Read contents | `read()`  | zero | `str` | `myFile.read()` |
| Read contents <br> as lines | `readlines()` | zero | a `list` of strings | `myFile.readlines()`  |
| Write to a `File` | `write()` | one `str` | nothing | `myFile.write('Hi\n')` |
| Close a `File` | `close()` | zero | nothing | `myFile.close()` |

Here is an example to read from a file:

```
fname = 'mysteryFile.txt'
myFile = open(fname,'r') # open for reading (file must exist)
text = myFile.read() # save entire file in text variable
myFile.close() # close the file
print(text) # print the text
```

Here is an example to write to a file:

```
fname = 'notamysteryFile.txt'
myFile = open(fname,'w') # open for writing (file can be new)
myFile.write('this is the first line\n') # write a string (remember the newline!)
myFile.write('...and this is the second line.\n')
myFile.close() # close the file
```
# Python Reference
Python is an interpreted high-level programming language with dynamic and strong typing disciplines. 
## Lexical Structure
### Whitespace and indentation
Use 4 spaces(U+0020) every indentation level. 

Space(U+0020) is preferred instead of Tab(U+0009) for indentation.

If you use mixing indentation of spaces and tabs in Python 3, it will result a indentation error.
In Python 2, tabs in the code will be converted to spaces.

The max line length should be limited to 79 characters (Excluding line feed and carriage return).

In this case, the proper format to include a extremely long name should be:

```python
with open('/path/to/a/extremely/long/name/file\
           /that/you/want/to/read.txt') as file_1:
    # do something here
    file_1.close()
```
Separate lines of a long expression:

```python
result = (calculate_result(param1, param2) - \
         100 * fixed_coefficient / \
         (large_int + another_large_int) + \
         addition_number)
# Or place operators after line break
result = (calculate_result(param1, param2)
         - 100 * fixed_coefficient
         / (large_int + another_large_int)
         + addition_number)
```
Imports also should be on separate lines:

```python
import os
import sys

# However, it is ok to import several 
# methods from a library on single line.
from library import method1, method2
```
For line break,

Surround top-level function and class definitions with two blank lines. 
Surround method definitions single blank line.

```python
# declare a function
def function1():
    pass
    
def function2():
    function1()
   
    
class no_name_class:

    def __init__(self):
        pass
        
    def method(self, param):
        pass
        
```
### Comments
There are two ways to comment a line in python
Starts with a `#` - `# This is a line of comment` or surrounds with triple `"` - `""" This is a line of comment """`
#### Block comments

```python
# Describe what we want to do next, 
# never describe the code itself
# eg. We use method to find out 
# the largest number in the array

def method(param):
    pass
```
#### Inline Comments
A least two spaces from the statement.

```python
x = (x + 1) & (y - 1);    # Increment on x or reset to 0 if x >= y
```

## Types
## Expressions
## Statements
## Declarations
## Attributes
## Patterns


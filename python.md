# Python Stylesheet
Python is an interpreted high-level programming language with dynamic and strong typing disciplines. 
## Layout
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

# However, it is OK to import several 
# methods from a library on single line.
from library import method1, method2
```
#### For line break,

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
#### Documentation Strings
Docstrings are the comments to describe methods, functions and classes.

```python
def merge_sort(arr, low, high):
    """Merge sort on array
    
    Detail information to describe the merge sort.
    
    Args:
        arr: an array to sort.
        low: start index of the array.
        high: end index of the array.
    Returns:
        A sorted array. 
        e.g.
        ......
        
    Raises:
        some_typeof_error: in what cases will the error occurs.
    """
    pass    # Method goes here
         
         
class SampleClassName(object):
    """Briefly describe the class
    
    Detail
    ...
    
    Attributes:
        
    """

```
## Naming Conventions
#### Package and module names

```python
# Lower case words with underscores (snake case)
import package_name
import module_name
```
#### Class names

```python
# Upper case words combined (pascal case)
class ClassName(object):
    
    __init__(self):
    pass
```
#### Exception names

```python
# Basically same as class names
class ExceptionName(Exception):

    pass
```
#### Global variable names

```python
global global_var_name
```
#### Function and variable names

```python
variable_name = 123

def function_name():
    pass
```
#### Function and method arguments

```python
class ClassName:
    
    def instance_method(self, ...):
        pass
    
    @classmethod
    def classMethod(cls, ...):
        pass
    
    @staticmethod
    def staticMethod():
        pass
        
```
#### Method names and instance variables

```python
def function_name(method_parameter_name):
    pass
```
#### Constants

```python
# All capital letters with underscores
CONSTANT_NAME = 123
```
#### Inherent methods

```python
# Includes __new__, __init__, __str__ ...
class ClassName(object):

    def __init__(self):
        pass
    
    def __str__(self):
        pass
        
```
## Statements
#### Conditional statements

```python
if some_conditions:     
    # some_conditions must return a boolean value
    pass
else:
    pass   
```

`if` statement can have multiple `elif` and `else` is optional.

```python
x = int(input("Please enter an integer: "))
if x > 0:
    print("Your input is positive")
elif x < -1:
    print("Your input is less than -1")
elif x < 0 and x >= -1:
    print("Your input is less than negative and larger than -1")
else:
    print("Your input is 0")
```
#### Loop statements

##### `for` statements:
```python
numbers = [1, 2, 3, 4, 5]
for number in numbers:
    print(number)
    
# Output is   
"""
1
2
3
4
5
"""
```
##### `while` statements:
```python
while some_conditions:
    # some_conditions must return a boolean value
    do_something()
```
In Python, there is no `do-while` loop, but you can implement it like this:

```python
while True:
    do_something()
    if fail_condition:
        break
```
#### Exception handling statements
```python
try:
    do_something()
except IOError:
    print("IOError occurs")
else:
    print("No IOError occurs")
finally:
    do_something_finally()
    # THIS WOULD ALWAYS BE EXECUTED
```
Raise an exception:

```python
raise ExceptionName(Error)
```
## Declarations
#### Variables

```python
integer = 1
float_number = 0.12345
pi = 3.1415
string = 'Hello'
object = function   # function object

global global_val   # a global variable
global_val = 123
```

#### Methods and functions

```python
class ClassName:

    def method(self):
        pass


def function():
    pass
    
# Call method and function
sample_class = ClassName()
sample_class.method()

function()
```
#### Constants

```python
CONSTANT_STRING = 'abc'
CONSTANT_INT = 123
```

#### Classes

```python
class ClassName(object):

    def __init__(self, param):
        self.param = param
        
    def method(self, param1, param2):
        return param1 + param2
        
    def __str__(self):
        return 'This is a class'
        
```
## Patterns
#### Wildcard pattern

```python
for _ in range(5):
    do_something()
```
Underscore (`_`) variable means throwaway in Python.

#### String pattern

```python
str1 = '%s, %d!' % ('Hello', 12345)
# str1: 'Hello, 12345!'
str2 = 'language: {}, version: {}'.format('Python', 3.6)
# str2: 'language: Python, version: 3.6'
string = str1 + str2
# string: 'Hello, 12345!language: Python, version: 3.6'
```
It is better to use `"""` for multiline strings instead of `'''`.

```python
# first way
print("This is a multiline string.\n"
      "This is the second line.\n")

# second way
print("""This is a multiline string.
This is the second line.
""")
```
Though they produce the same outputs, the first one is better in this case. 

#### List and Dictionary pattern

```python
empty_list = []

integer_list = [1, 2, 3, 4, 5]
string_list = ['a', 'b', 'hello']
mixed_list = [1, 'hello', 1.5, (1, 'tuple'), ['banana', 1000]]

matrix = [
    [1, 2, 3, 4],
    [2, 4, 6, 8],
    ]
```
Dictionary in Python is similar to JSON object.

```python
dictionary = {}     # an empty dictionary
example_small = {'key': 'value', 'number': 2}
example_large = {
    'key1': 'value1',
    'key2': 'value2',
    ...
                
}
```
#### Regular expression


## References
1. [PEP 8](https://www.python.org/dev/peps/pep-0008), Style Guide for Python Code, van Rossum
2. [Naming convention (programming) - Wikipedia](https://en.wikipedia.org/wiki/Naming_convention_(programming))
3. [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html), Amit Patel, et al.



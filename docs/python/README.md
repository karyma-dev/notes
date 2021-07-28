# Python

Interpreted language, saves time because no compilation or linking necessary, tradeoff compared to complied languages is that it is generally slower. Python is an dynamic typed programming language.

## Features

### General

-   User Input, will always store value as a string
    -   `x = input('What is your name?')`
-   Comments
    -   `#This is a comment`{.python}
-   `type(x)`
    -   returns the data type of variable

### Operators

-   Arithmetic Operators

    -   `+`
    -   `-`
    -   `*`
    -   `/`
    -   `//`
        -   Floor division, rounds down the result of division
    -   `**`
        -   Exponents
    -   `%`
        -   Modulus, gives remainder of division

-   Comparison Operators

    -   `==`
    -   `!=`
    -   `>`
    -   `>=`
    -   `<`
    -   `<=`

-   Assignment Operators

    -   `=`
    -   `+=`
    -   `-=`
    -   `*=`
    -   `/=`
    -   `%=`
    -   `//=`
    -   `**=`

-   Logical Operators

    -   `and`
    -   `or`
    -   `not`

-   Membership Operators  
    _These operators provide and easy way to check if certain object is present in a sequence: string, list, tuple, set and dictionary._ - `in` - returns `True` if object is present - `not in` - returns `True` if object is not present

### Conditionals

Controls the program flow of your application, examples [here](./Examples/Conditionals.py)

-   `if` `elif` `else` statement
-   Ternary Operators, 1 line if statement
    -   `result = a if True else b`

### Boolean

-   Boolean Declarations
    -   `x = True`
    -   `x = bool(1024)`

### Int

-   Int Declarations
    -   `x = 1`
    -   `x = int(1)`
-   `int(x)`
    -   Explicit conversion, converts string into a number, if float value it will always round down

### Float

-   Float declarations
    -   `x = 3.2`
    -   `x = float(3.2)`
-   `float(x)`
    -   Explicit conversion, convert int or string into a float value

### Complex

-   Complex declarations
    -   `x = 32+4j`
    -   `x = complex(32+4j)`

### Strings

-   String declarations
    -   `x = 'string'` can be single or double quote
    -   `x = str('string')`
-   `str(x)`
    -   Explicit conversion, converts number to string whether it is a float or int
-   `\` Backslash is used to escape characters.
    -   `print('Don\'t')`
-   Raw string, ignores backslashes
    -   `print(r'C:\some\name')`
-   `len(x)`
    -   returns the length of the string
-   `x.replace(y, z)`
    -   replaces y with z in a string and returns the new output
-   `x.upper()`
    -   returns string with all uppercase characters
-   `x.lower()`
    -   returns string with all lowercase characters
-   [String Literals](./Examples/StringLiteral.py)

### Lists

Ordered, mutatable and allows repetition

-   List declarations
    -   `x = []`
    -   `x = [item1, item2]`
    -   `x = list((item1, item2))`
-   Adding in a list
    -   `x.append(y)`
-   Insert item at index
    -   `x.insert(index, value)`
-   Updating in a list
    -   `x[index] = value`
-   Deleting item in a list
    -   `x.remove(value)`
-   Clearing a list
    -   `x.clear()`
-   Retrieving item in a list
    -   `x[index]`
-   Checks if item is in list
    -   `<value> in x`

### Tuples

Ordered and allows repetition but immutable, example [here](./Examples/Tuples.py)

-   Tuple declarations
    -   `x = ()`
    -   `x = ( item1, item2 )`
    -   `x = tuple((item1, item2))`
-   Updating a Tuple
    -   Must first convert to list then back to a tuple
-   Retrieving item from tuple
    -   `x[index]`
-   Check if item is in tuple
    -   `<value> in x`

### Dictionaries

Unordered, key value pairs and mutable

Dictionary declarations - `x = {}` - `x = { "key": "value, key2: "value" }` - `x = dict(key = "value", key2 = "value")`

-   Adding item to dict
    -   `x[key] = value` if key does not exist in dict
-   Updating item in dict
    -   `x[key] = value` if key already exist in dict
-   Removing item from dict
    -   `x.pop(value)`
-   Retrieving item from dict
    -   `x[key]`
-   Clearing all items in a dict
    -   `x.clear()`
-   Check if key exist in dict
    -   `<key> in x`

### Sets

Unordered, items are not indexed and they don't allow repetition of items

-   Sets declarations
    -   `x = set()`
    -   `x = { "strings", numbers }`
    -   `x = set(("strings", numbers))`
-   Adding single item to set
    -   `x.add(value)`
-   Adding multiple item to set
    -   `x.update([value1, value2])`
-   Updating set
    -   Items in a set are immutable, you have to either add or delete an item
-   Deleting item from a set
    -   `x.remove(value)`
-   Clearing all items from a set
    -   `x.clear()`
-   Check if item is in set
    -   `<value> in x`

### Loops

-   `for` loops

    -   ```python
        for item in collection:
            <do something>

        for number in range(5):
            <do something>
        ```

-   `while` loops, will loop until condition is True
    -   ```python
         i = 0
         while i <= 5:
             <do something>
             i += 1
         else:
             print('i is greater than 5')
        ```
-   `break` keyword breaks out of loop
-   `continue` keyword will skip to the next iteration of the loop

### List Comprehension

```python
[expression for item in list if conditional]

# same as below

for item in list:
    if conditional:
        expression
```

### Functions

-   Defining a function
    -   `def functionName():`
-   `return` keyword is used to return value from a function
    -   may return multiple values with `return a,b`
-   Default values for parameters
    -   `def functionName(x = 'defaultValue')`
-   Any number of arguments
    -   ```python
          def functionName(*args):
              for arg in args:
                  print(arg)
        ```
-   Any number of keyword/named arguments:
    -   ```python
          def functionName(**kwargs):
              for key, value in kwargs.items():
                  print(key)
                  print(value)
        ```

### Lambda Functions

-   Python lambda functions are anonymous and can only have one expression. Example [here]('./Examples/Lambda.py)
-   `lambda arguments: expression`

### Classes

-   Creating a class
    -   `class className:`
-   Creating a class object
    -   `x = ClassName(<optional>)`
-   Inheritance
    -   `class Child(Parent):`
-   It good practice to name your files after your classses
-   Most of the time you will see `self` as the first argument, it is the reference to the current object that is created
-   `__init__`
    -   initialization is called whenever object is created, often used to initialize attributes

### Modules

-   To export simply just import filename, no export keyword needed. [Exporting Example](./Examples/Module_Export.py) and [Importing Example](./Examples/Module_Import.py)
-   `import` keyword to import module
-   `as` keyword for creating an alias for module
-   `from` keyword imports specific classes or methods from module
-   ```python
      from math import floor

      floor(9.68)
    ```

### Exceptions

Types of Exceptions

-   `TypeError`, `IndexError`, `NameError`, `ZeroDivisionError`
-   `raise` keyword allows you to manually raise an exception
    -   ```python
          try:
              raise IndexError('This index is not allowed')
          except:
              print('Doing something with the exception!')
              raise
        ```
-   `finally` block is executed whether exceptions being raised or not
    -   ```python
          try:
              print(my_variable)
          except NameError:
              print('Except block')
          finally:
              print('Finally block')
        ```

### Files

-   `file_name = open('filename', '<2nd Argument>')`
-   If 2nd Argument is:
    -   `x` create a file and will throw an exception if file already exist
    -   `w` create a file if file does not exist or overwrite existing file
    -   `a` append data to the file or create if file does not exist
    -   `r` read file if file does not exist it will throw an error
-   `write` mode
    -   ```python
          file_name = open("filename", "w")
          file_name.write("Hello World \n")
          file_name.close()
        ```
-   `append` mode
    -   ```python
          file_name = open("filename", "w")
          file_name.write("Hello World \n")
          file_name.close()
        ```
-   `read` mode

    -   ```python
          file_name = open("filename", "r")
          # Read whole file
          print(file_name.read())
          # Read One line at a time
          print(file_name.readline())

          # Can loop through every line
          for item in  file_name:
              print(item)
        ```

-   To delete files you must have the `os` module
    -   ```python
          import os
          os.remove('file_name')
        ```
-   To check if file exist

    -   ```python
          import os

          if os.path.exists('file_name'):
              os.remove('file_name')
          else:
              print('There is no such file!')
        ```

-   Copying Files

    -   ```python
          from shutil import copyfile

          copyfile('file_name', 'another_file')
        ```

-   Rename and move a file

    -   ```python
          from shutil import move

          move('file_name', 'another_file')
        ```

### Stuff

-   [range()](./Examples/range.py)

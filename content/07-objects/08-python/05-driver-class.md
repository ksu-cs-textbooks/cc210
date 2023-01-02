---
title: "Driver Class"
pre: "5. "
weight: 50
---

The Driver class is much simpler.  It has one feature, a **class method** `main(cls, args)`.  Everything that needs to be done will be done in the main method.  A template might be

```python
import sys

class Driver:
    
    @classmethod
    def main(cls, args):
        pass
    

if __name__ == "__main__":
    Driver.main(sys.argv)
```

{{% notice info "Decorators in Python" %}}

Previously we ave been using the decorator[^1] `@staticmethod` for `main`.  It turns out that Python implements "static methods" very differently than most other languages.  To get the same "effect" of a Java or a C# "static method" we will need to use `@classmethod` instead.  You only need to know three things about class methods right now:

1. They are decorated with "@classmethod" as the first line of their definition
2. They <b>ALWAYS</b> have `cls` as their first parameter, the parameter list is never empty
3. Like `self` with instance classes, the `cls` is automatically passed when the function is called.  Do not include a value for it at the call site. `Driver.main(sys.argv)` has an argument for `args` in `main(cls, args)` but not `cls`.

[^1]: Decorators provide special instructions to the interpreter

{{% /notice %}}

## Accessing the Instance Class

Lets add an instance `Ingredient` as `i1`

```python
@classmethod
def main(cls, args):
    i1 = Ingredient()
```

If we try to access the instance class right now we would get a `NameError: name 'Ingredient' is not defined`.  Identifier scope in Python goes[^2] 

1.  current method
1.  `.py` file of current method, this includes anything imported 
1.  the built-in keywords and functions

[^2]: Dogmatically it goes Local, Enclosing, Module, Built-in.  We aren't going to go into "Enclosing" at all, and the differences between Module and file are small and super technical.

Since the interpreter does not find  `Ingredient` defined inside `main()`[^3], or in the file (outermost indention level) or in the built-in functions, it throws an error.  We need to import `Ingredient.py`.

[^3]: We will not defining any methods within methods in the course

#### `import module`

The Python when you use the `import <file_name>` key word, the interpreter searches for a file `<name>.py`.  If the interpreter finds the file[^4], it imports the entire contents, which can be accessed using the name <file_name>.<feature_name>.  .   For example, math functions 

```python
import math

class Example:
    
    @classmethod
    def main(cls, args):
        x = math.sqrt(26.0)
        y = math.pi
        
```

[^4]: The interpreter first looks in the directory where the executing file is located.  This is how we will use it.

Every definition in `math`, and there are 54 of them, is available in the program as `math.<item>`. So one option is to 

```python
import sys
import Ingredient
import math

class Driver:
    
    @classmethod
    def main(cls, args):
        i1 = Ingredient.Ingredient()
        x = math.sqrt(36)
```

This is the safest and clearest way to import. 

#### `from module import feature`

Another way is to just import the few things you want from the module.  This adds the feature name to your file without needing use `module.`  

```python
import sys
from Ingredient import Ingredient
from math import sqrt
class Driver:
    
    @classmethod
    def main(cls, args):
        i1 = Ingredient()
        x = sqrt(36)
            
```

This can lead to shorter programs at the expense of clarity.  When a reader sees `math.sqrt` they know what you are using, when they see `sqrt`  they need to "read up" in the program to see where it is defined.

<p style ="font-size: 150%">In this class use `import module_name`!  </p>

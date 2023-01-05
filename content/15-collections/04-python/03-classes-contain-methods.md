---
title: "Classes Contain Methods"
pre: "3. "
weight: 30
---

Sometimes we just want a collection of associated methods -- think math.pi.   In Python we could accomplish this by having a class that has no class or instance attributes and only static methods.  Raymond Hettinger, a Python Language developer goes so far as to say the purpose of `@staticmethod` is to attach methods to classes[^1]

[^1]: Python Class Development Toolkit at https://www.youtube.com/watch?v=HTLu2DFOdTg&ab_channel=NextDayVideo.


So in Python a "bucket" of 
```python
class my_math:
    @staticmethod
    def pi():
        return 3.1416

    @staticmethod
    def circle_area(radius):
        return radius * radius * my_math.pi()
```

Here we have a static method that returns a value for &pi;.  This is my personal method for establishing a constant[^2]. This avoids the situation where pi can be overwritten.

[^2]: Python has been described as a language for consenting adults--there is no privacy and there are no constants.  Every value and method can be accessed changed by a determined programmer


```tex
.WIN2>python
Python 3.9.10 (tags/v3.9.10:f2f3f53, Jan 17 2022, 15:14:21) [MSC v.1929 64 bit (AMD64)] on win32
>>> import math
>>> print(math.pi)
3.141592653589793
>>> print(math.sin(math.pi))
1.2246467991473532e-16  # essentially the correct answer (0.0) 
>>> math.pi =2.0
>>> print(math.sin(math.pi))
0.9092974268256817 # very much not zero
>>>
```

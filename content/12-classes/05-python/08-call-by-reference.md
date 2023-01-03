---
title: "Call by Reference"
pre: "8. "
weight: 80
---

Finally, it is important to remember that any instantiated objects used as arguments to a method are passed in a _call-by-reference_ manner. So, any modifications to those objects made inside of a method will also be reflected in the code that called the method.

Here's a quick example:

```python
class Reference:
  
  def __init__(self):
    self.x = 0
```

```python
from Reference import *

class Main:
  
  @staticmethod
  def main():
    some_ref = Reference()
    some_ref.x = 10
    Main.modify(some_ref)
    print(some_ref.x)  # 15
    
  def modify(a_ref):
    a_ref.x = 15
    
if __name__ == "__main__":
    Main.main()
```

As we can see, when we call the `modify()` function and pass a `Reference` object as an argument, we can modify the attributes inside of that object and see those changes back in the `main()` method after `modify()` is called. 

Of course, if we reassign the argument's variable to a new instance of `Reference` inside of the `modify()` function, then we won't see those changes in `main()` because we are dealing with a newly created object. 

{{% notice info "Call by Object Reference" %}}

In many examples, Python exhibits behavior very similar to "call-by-reference" as discussed in other programming languages. However, because Python allows both mutable and immutable objects, there are some subtle differences in how it handles objects stored in variables compared to languages like Java and C++.

One developer has proposed the term _call-by-object-reference_ to help clarify the difference. You can read more on [his blog](https://jeffknupp.com/blog/2012/11/13/is-python-callbyvalue-or-callbyreference-neither/).

For now, we'll continue to use the term _call-by-reference_ since it has a standard usage across many programming languages. When in doubt, it is always a good idea to write a simple test case and make sure the program you are developing works as expected. 

{{% /notice %}}

So, we'll need to keep this in mind as we use objects as parameters and returned values in any methods we create in our programs.


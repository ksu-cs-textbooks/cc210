---
title: "More on Parameters"
pre: "3. "
weight: 30
---

{{< youtube yg8mUiYpHLg  >}}

[Video Materials]({{% relref "./video" %}})

<!-- TODO Update Video -->

There are several other things we can do with parameters in our methods, allowing us to use them in new and more flexible ways.

## Methods using Default Values

Python allows us to specify default values for parameters in a method definition. In that way, if those parameters are not provided, the default value will be used instead. So, it may appear that there are multiple methods with the same name that accept a different number of parameters.

For example, we could create a method named `max()` that could take either two or three parameters:

```python

class Default:
    def main(args):
        Default.maximum(2, 3)
        Default.maximum(3, 4, 5)
      
    def max(x, y, z=None):
        if z is not None:
            if x >= y:
                if x >= z:
                    print(x)
                else:
                    print(z)
            else:
                if y >= z:
                    print(y)
                else:
                    print(z)  
        else:
            if x >= y:
                print(x)
            else:
                print(y)
      
# main guard
if __name__ == "__main__":
    Default.main()
```

In this example, we are calling `max()` with both 2 and 3 arguments from `main()`. When we only provide 2 arguments, the third parameter will be given the default value `None`, which is a special value in Python showing that the variable is empty. Then, we can use `if z is not None` as part of an **If** statement to see if we need to take that variable into account in our code. 

This example also uses a new keyword, `is`. The `is` keyword in Python is used to determine if two variables are exactly the same object, not just the same value. In this case, we want to check that `z` is exactly the same object as `None`, not just that it has the same value. In Python, it is common to use the `is` keyword when checking to see if an optional parameter is given the value `None`. We'll see this keyword again in a later chapter as we start dealing with objects. 

## Keyword Arguments

Python also allows us to specify method arguments using keywords that match the name of the parameter in the method. In that way, we can specify the arguments we need, and the method can use default values for any unspecified parameters. Here's a quick example:

```python
class Default:
    def main():
        Default.foo2(1)             # 6
        Default.foo2(1, 5)          # 9
        Default.foo2(1, c=5)        # 8
        Default.foo2(b=7, a=2)      # 12
        Default.foo2(c=5, a=2, b=3) # 10
  
    def foo2(a, b=2, c=3):
        print(str(a + b + c))
      
# main guard
if __name__ == "__main__":
    Default.main()
```

In this example, the `foo2()` method has one required parameter, `a`. It can either be provided as the first argument, known as a _positional argument_, or as a _keyword argument_ like `a=2`. The other parameters, `b` and `c`, can either be provided as _positional arguments_ or _keyword arguments_, but they are not required since they have default values. 

Also, we can see that when we use keyword arguments we do not have to provide the arguments in the order they are defined in the method's definition. However, any arguments provided without keywords must be placed at the beginning of the method call, and will be matched positionally with the first parameters defined in the method. 

{{% notice info "This is Not Overloading a Method" %}}

You may hear of languages that allow method "overloading".  This is when a language allows, in the same scope, two methods to have the same name as long as they have different parameter lists. Something like

``` tex
def foo(a, b):
    ...

def foo(a):
    ...
```
But Python allows re-definition, so while in Java you would end up with two methods called `foo`, in Python the second definition `foo (a)` would overwrite the first definition `foo (a, b)`.  Because Python allows re-definition it cannot allow overloading.

Some languages, notably C#, allow both overloading and default/named/variable parameters.

{{% /notice %}}

## Try It!

Let's see if we can use this knowledge to build a program that uses method overloading with both default values and variable length arguments. In Default.py, create a class `Default`.  Include:

1. `main(:list)` method that accepts the command line arguments. It should use `print_repeat` to print the word "Hello" 4 times, and then the lines "Good Morning" and "Good Afternoon" alternating one after the other, a total of 3 times each. 

1. `print_repeat(:int, :str, :str)` that accepts three parameters, an integer and two strings. This method will repeatedly print the first string, followed by the second string, each on separate lines, as many times as indicated by the integer parameter. The second string should be an optional argument, with a default value of `None`. 

In each case, if the integer is $0$ or less than $0$, the method shouldn't print anything.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

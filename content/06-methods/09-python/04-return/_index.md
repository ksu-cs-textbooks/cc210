---
title: "Return"
pre: "4. "
weight: 40
---

<!-- {{% youtube sbsUDbRyh6o %}} -->

<!-- TODO Update Video --> 

<!-- [Video Materials]({{<relref "./video">}}) -->

Lastly, we can have methods in our code _return_ a value from a method. This allows us to use a method to perform an action or calculation that results in a single value that we can use elsewhere in our code. We can even use these method calls just like we use variables in other arithmetic expressions. Let's take a look at how that works.

## Returning a Value

To return a value from a method in Python, we use the special keyword `return`, followed by an expression representing the value we'd like to return. Here's an example program showing how to use the `return` keyword and store that returned value in a variable. 

```python
class IdealGas:

    @staticmethod
    def main():
        temp_K = 273
        vol_l = 22.4
        return_value = IdealGas.pressure(temp_K, vol_l)
        print(return_value)

    @staticmethod 
    def pressure(t, v, n=1):
        r = 8.31446261815324
        if v == 0:
            return None
        p = n*r*t/v
        return p

if __name__ == "__main__":
    IdealGas.main()
```
{{% notice info "method Signature" %}}

Like parameters, the intended return type can be added.

```
def add (x: int, y:int) -> int:
    return x + y
```

Here `add` is saying that the author intended for it to take two integers and return an integer.  You will note that the method doesn't crash if passed two floats, bools or strs.  However it may not return an int if passed non-ints as arguments.

The line `def add (x: int, y:int) -> int:` is often referred to as a **method signature**.  It contains all the vital information necessary to use the method: its name, what it returns, and what type of parameters it requires.  

{{% /notice %}}

The program above calculates the pressure (in Pascal) for a gas at a certain temperature (in degrees Kelvin) occupying a specified volume (in liters).  Let's review this program carefully to see what parts of the program are important for returning a value:

1. We note that the pressure method defaults to a value of n = 1.  `n` refers to the number of moles^[a mole of gas is 6.02 x 10<sup>23</sup> molecules.] of gas in question. 
1. Inside of the `pressure()` method, we see two instances of the `return` keyword. Each instance is followed by a value or expression, which is then returned from the method. As soon as the method reaches a `return` keyword, it immediately stops executing and returns that value. So if the volume of a gas is zero or less (a physical impossibility), pressure returns `None`--this make sense since there is pressure that can collapse a gas to a negative volume.  Otherwise `pressure` calculates the pressure and returns that value to the call site. 
1. In the `main()` method, we see that we've included the method call to `pressure()` on the right-hand side of a variable assignment statement. So, once we reach that line of code, the program will call the `pressure()` method and store the returned value in the `returnValue` variable in `main()`.

{{% notice note "Python Style" %}}

According to [PEP8](https://www.python.org/dev/peps/pep-0008/): Be consistent in return statements. Either all return statements in a function should return an expression, or none of them should.

```python

#correct
def foo(x):
    if x >= 0:
        return math.sqrt(x)
    else:
        return None

#wrong
def foo(x):
    if x >= 0:
        return math.sqrt(x)
```

When you don't want to return anything, explicitly return `None`.  In CC 210, we do not grade on this, but you should get into this habit.

{{% /notice %}}

## Try It!

Let's try one more example, just to get some more experience building methods that return a value.

For this exercise, let's write a program takes two command line arguments, a number representing the temperature in degrees and a letter ("F" or "C") representing the temperature scale, either Fahrenheit or Celsius that contains the following and displays it as degrees Kelvin.  This program must contain:

1. A class Return that has two static methods: `main(:list)` and `convert2_K(:float, :str) -> float`.
1. A `main()` method should convert the passed in parameter to the appropriate type, call `convert2_K`, capture its return value and print it as a real number.  Use the statement `print("{:.2f} K".format(<variable>))` to display in degrees Kelvin.
1. A method `convert2_K()` that accepts a number and a a single character (a string with length 1) as parameters. The method should then return a float that gives value of the temperature in degrees K(elvin).
   1. degrees Kelvin = degrees Celsius + 273.15
   1. degrees Kelvin = (degrees Fahrenheit -32) * 5 / 9 + 273.15
3. The program should have a main guard that passes the command-line arguments to the program as an argument to `main()`.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}
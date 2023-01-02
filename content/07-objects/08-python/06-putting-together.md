---
title: "Putting it All Together"
pre: "6. "
weight: 60
---


First set the default values in `Ingredient.__init()` to: "flour". 2.75, "cups".


Next lets write a driver program which takes 2 command line arguments, a scale factor and a units string, and prints out the ingredient list for sugar cookies.
The basic ingredients are 
* i1 (flour", 2.75, "cups")
* i2 ("butter", 1, "cups")
* i3 ("sugar", 1.5, "cups")
* i4 ("baking powder", 2.6, "ml")
* i5 ("baking soda", 15.0, "ml")
* i5 ("vanilla extract", 15.0, "ml")

A typical run might look like:
```
$ python3 Driver.py 1 cups
2.75 cups of flour
1.00 cups of butter
1.50 cups of sugar
0.01 cups of baking powder
0.06 cups of baking soda
0.06 cups of vanilla extract
```

## Setting up the Driver Program

First we write the generic driver program and class skeleton:

```python
import sys
import Ingredient


class Driver:
    
    @classmethod
    def main(cls, args):
        pass

    
if __name__ == "__main__":
    Driver.main(sys.argv)
```

## Handling the Command Line

Our program takes 2 command line arguments,  Since it is reasonable to assume that a recipe can be halved or doubled, the scale-factor should be converted inot a float.  We know from the UML that the conversion method expects a string, so no conversion is necessary.

```python
@classmethod
def main(cls, args):
    factor = float(args[1])
    units = args[2]
```

## Handling an Ingredient

Lets use `i2` as an example.  First we will need to create an object.  We will need to adjust its attributes from the default.  Next we will create a new object, 12_scaled using `.scale()`; then convert i2_scaled to the proper units.  Finally, we will need to print it out.


```python
@classmethod
def main(cls, args):
    factor = float(args[1])
    units = args[2]

    # create the orignal ingrd objects
    i2 = Ingredient.Ingredient()
    
    # modify the orignal ingrd objects as necessary
    i2.name = "butter"
    i2.amount = 1.
    i2.units = "cups"

    # create the scaled ingrd objects
    i2_scaled = i2.scale(factor)

    # convert the sclaed ingr obj to teh correct units
    i2_scaled.convert(units)

    # print the scaled, converted objects in order
    print(i2_scaled.toString())
```

## You do it

Finish the program.  When you are done, check it for 10 points. The check will verify both the structure and functionality of `main()`.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

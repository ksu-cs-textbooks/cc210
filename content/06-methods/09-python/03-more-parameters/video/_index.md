---
title: "Python Overloading"
pre: "5.P. "
weight: 51
date: 2019-09-23T00:00:26-05:00
hidden: true
---

{{< youtube AOtnZGIqsaQ >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

One of the most useful features of functions in Python is the ability to _overload_ a function name by providing parameters with a default value. So, the function could be called with different sets of arguments, and as long as the Python interpreter can determine which arguments match up with the parameters listed, it will work.

This code gives a great example of how this could work in Python. We've created a function named `max()`, and defined three parameters. The third parameter, `z`, is given a default value of `None`, a special value in Python that represent an empty variable. So, in this code, the parameters `x` and `y` are required since they don't have any default values, but the third parameter `z` is not required when calling the `max()` function.

So, when we run this program by starting in the `main()` function, we immediately see a function call for a function named `max()`. In this case, the program will examine the function definition for `max()` and see what parameters are expected. Since we've provided two arguments, we see that it will work because the function only requires 2 parameters. So, inside of that `max()` function, the variables `x` and `y` will be set to the values 2 and 3, respectively, while the value of `z` will be set to `None`. Then, in our code, we can use that value of `None` to determine if a value was provided for `z`, and adjust our code accordingly.

On the next line of the `main()` function, we see a call to the function named `max()` with three arguments provided. The program will go through the same process as before, but this time it see that the definition of `max` can also accept three parameters, and will set the values of those parameters using the arguments as provided.  

Python also allows us to define a function that accepts a variable number of parameters. However, we must carefully remember that each function can only have one of these variable length parameters, and it must be the last parameter defined.

When we call this function, we can provide any number of integer arguments. Those arguments are stored in a list called values inside of `max()`, and the size of the list is set to exactly match the number of arguments provided. So, in the function's code, we can use a for loop to iterate through each variable in the list.

Therefore, no matter how many arguments we provide, this `max()` function will be able to handle it and calculate the correct answer. It is a very powerful method to build functions that can accept a wide range of data as input.

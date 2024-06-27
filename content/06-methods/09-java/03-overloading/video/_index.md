---
title: "Java Overloading"
pre: "5.J. "
weight: 50
date: 2019-09-23T00:00:26-05:00
hidden: true
---

{{< youtube bEVjtEc4IZM >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

One of the most useful features of functions in Java is the ability to _overload_ a function name with multiple declarations. As long as each declaration uses a different list of parameters, the program can easily determine which version of the function to use.

This code gives a great example of how this could work in Java. We've created two functions named `max()`, one that accepts two integers as parameters, and the other that accepts three integers.

So, when we run this program by starting in the `main()` function, we immediately see a function call for a function named `max()`. In this case, the program will find all of the function declarations that have the name `max` first. Since there are more than one of them, it will then check the number and types of arguments provided against the parameters in each function declaration, looking for a match. Since we've provided two arguments, the version of `max()` that accepts two parameters is chosen. So, inside of that `max()` function, the variables `x` and `y` will be set to the values 2 and 3, respectively.

On the next line of the `main()` function, we see a call to the function named `max()` with three arguments provided. The program will go through the same process as before, but this time it will choose the version of `max()` that accepts three parameters, and will set the values of those parameters using the arguments as provided.  

Java also allows us to define a function that accepts a variable number of parameters. However, we must carefully remember that each function can only have one of these variable length parameters, and it must be the last parameter defined. In addition, all arguments provided to a variable length parameter must be the same type, since they will all be stored together in the same array. Finally, it cannot conflict with any other function declaration, so if we defined a function named `max` that accepted just one integer, that definition would conflict with this one since both functions could accept the same arguments.

When we call this function, we can provide any number of integer arguments. Those arguments are stored in an array called values inside of `max()`, and the size of the array is set to exactly match the number of arguments provided. So, in the function's code, we can use a proper enhanced for loop to iterate through each variable in the array.

Therefore, no matter how many arguments we provide, this `max()` function will be able to handle it and calculate the correct answer. It is a very powerful method to build functions that can accept a wide range of data as input.

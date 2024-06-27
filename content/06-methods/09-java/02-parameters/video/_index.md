---
title: "Java Parameters"
pre: "4.J. "
weight: 40
hidden: true
date: 2019-09-23T00:00:26-05:00
---

{{< youtube O-vkFmelepU >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

What if we need to provide some input data to our functions? In that case, we can add one or more parameters to the function declaration. Let's look at an example.

In this code, we've added a variable declaration inside of the parentheses of our function declaration. In Java, we need to include both a type and a variable identifier.

Then, in our code, we can use that variable identifier just like any other variable. The value it will contain depends on the argument provided to the function when it is called.

For example, if we call the function `foo()` with the argument "Hello World", that string will be stored in the message parameter inside of the function.

We can even take it a step further and look at a more complex example. Let's walk through this code step by step and see how the data is shared between functions. As always, we'll start in the `main()` function. First, we set the values for three variables, `x`, `y`, and `z`. Since those variables are declared in the `main()` function, we'll need to list them under the `main` heading in our variable list.

Next, we'll call the `bar()` function, using the variables `x`, `y`, and `z` as arguments. So, our program will look for the declaration of the function named `bar()`, and match up each argument with the parameter in the same position. That will cause the value in `x` to be stored in `a`, `y` in `b`, and `z` in `c`. Those new variables, `a`, `b`, and `c`, are declared as part of the function `bar()`, so once again we'll list them under the `bar` heading in our variable list.

Once inside `bar()`, the code will print those values to the screen, and then the function will terminate and control goes back to the `main()` function.

Next, it will call the function `foo()` providing the variable `y` and the value `true` as arguments. Just like before, the program will find the function declaration for `foo()` in the code, and match up each argument with a parameter. So, in `foo()`, we'll see that the variable `output` is given the value stored in `y`, and the Boolean `longMessage` is given the value `true`.

Adding parameters to our functions is a great way to make our code that much more useful. See if you can do the same in the example on this page.

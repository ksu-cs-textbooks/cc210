---
title: "Java Return"
pre: "6.J. "
weight: 60
date: 2019-09-23T00:00:26-05:00
hidden: true
---

{{< youtube cL5GHtZ7VUw >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

We can also give our functions the ability to _return_ a value, such as the result of a calculation, back to the code where it was called from. By doing so, a function call can actually produce a value that can be stored in a variable and used elsewhere.

This code gives a quick example of what that would look like. Let's step through this code and see how it works. As always, we'll start in the `main()` function.

The first line of code is actually a variable assignment statement. But, before we can store a value in the `returnValue` variable, we must call the `last` function and get the result.

In the `last` function, we provide it a set of numbers as arguments, and it will return the last one. So, once we reach a `return` keyword, we'll identify that value and "pass it back" to the `main()` function as the result of this function call. In effect, we can replace the code with the function call with the value that is returned, just like we learned how to do earlier in this course when evaluating mathematical expressions in code. So, we'll store the value 9 in the variable `returnValue`, since that is what was returned from the function `last()`

One other important thing to notice is that this function includes a second return statement, `return -1` at the end of the code and outside of the If-Then statement. Java requires that all possible code paths through a function return a value. So, what if we call the `last()` function without any parameters provided? In that case, it will not enter the true branch of the If-Then statement, so we need to include a return statement outside of the If-Then statement to handle this case. Thankfully, the Java compiler will warn us if we forget to do this.

At this point, we've covered many important features of functions in our programs: we can define functions, create parameters, and return values. We can even overload functions using different sets of parameters, or accept a variable number of parameters in our functions. All of these are very helpful techniques as we start building larger programs.

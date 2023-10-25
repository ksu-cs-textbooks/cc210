---
title: "Creating Exceptions"
pre: "5. "
weight: 50
---

We can also create our own exceptions to handle specific situations in our own programs. Consider the following program flowchart:

![Creating Exception Flowchart](/images/10-except/8.5.throw.png)

In this program, we first accept input from the user. Then, if that input is less than $0$, we create an exception (as indicated by the triangle containing `Err` in the flowchart). If the input is greater than or equal to 0, we'll just output it. 

Of course, creating an exception in this way is probably not the best way to go about this. Instead, we could probably just use an **If** statement to achieve the same result. In fact, we already have one in our code!

However, as we start building larger and more complex programs, we may find it very useful to be able to create our own exceptions in one part of the program, then detect and handle them somewhere else. It would be impossible to do this with a simple **If** statement. 
---
title: "Java Instantiation"
pre: "5.J. "
weight: 50
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube f_7M2_RTcjI >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Now that we've added attributes and methods to our classes, we can explore how to use them in our programs.

In Java, we can use the `new` keyword to create an instance, or object, based on a class. So, if we want to create an object from the Student class, we would use the line `new Student()`

Of course, this line doesn't really do much, since we aren't storing the resulting object anywhere. Thankfully, as we learned earlier in this chapter, each class we create is actually defining a new data type that we can use to store objects as variables in our programs. So, we'll just need to create a variable that uses the data type `Student`, and assign the new Student object to that variable.

Once we've created the object, we can access any attributes or methods using "dot notation". Basically, we start with the name of the variable containing the object, then use a dot or period, then we can reference the attribute or method we'd like to use. In this example, we are accessing the `name` attribute of the Student object stored in the variable `jane`.

We can also treat those attributes just like any other variable, so we can assign a value to them as shown in this line of code.

So, we can easily add code to change any of the attributes of the student stored in `jane`.

Finally, we can access any of the methods in the Student object stored in `jane` in the same way. At the bottom of this example, we can see code calling the `birthday()` and `grade()` methods on that object.

As we continue in this module, we'll see more and more examples of instantiating objects based on our classes. By the end of this module, it should be a very familiar process.

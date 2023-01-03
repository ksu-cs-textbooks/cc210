---
title: "Python Instantiation"
pre: "5.P. "
weight: 51
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube rmvIVHuBdCw >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Now that we've added attributes and methods to our classes, we can explore how to use them in our programs.

In this example, we're assuming that we are writing code in a separate Python file from the one that contains our class. While this isn't required, it is a very good practice to get into, since most other programming languages follow the same structure. However, we are assuming that those files are contained in the same directory on the filesystem in this case.

To use a class that is defined in another file, we'll need to import it. For example, if the file is named "Student.py", we would use the line `from Student import *` at the top of our Python file. That will import everything defined in the `Student` file and allow us to use those items in our code. In addition, this is why it is important to use a main guard in our files. When we import code in this way, it will execute any code contained in the file that is not inside of a class or function. So, we can place our code in a function and use a main guard to call that function if we run the file directly, but it won't execute if we import the file. Pretty neat, right?

We'll add a similar line to import the Teacher class defined in "Teacher.py" as well.

Finally, since we are learning to write our own classes, we'll make a class called Main here to store our code, and inside of that class we'll also create a `main()` method. This will give our programs a much more convenient structure.

Of course, we'll also need to update our main guard to call the `main()` function inside of the Main class. We can refer to the code at the bottom of this example to see how that is done.

To create an object based on a class in Python, we can simply call the class like a function. This actually calls the class's constructor, which we'll learn about in a later video. So, if we want to create an object from the Student class, we would use the line `Student()`

Of course, this line doesn't really do much, since we aren't storing the resulting object anywhere. Thankfully, as we learned earlier in this chapter, each class we create is actually defining a new data type that we can use to store objects as variables in our programs. So, we'll just need to create a variable and assign the new Student object to that variable.

Once we've created the object, we can access any attributes or methods using "dot notation". Basically, we start with the name of the variable containing the object, then use a dot or period, then we can reference the attribute or method we'd like to use. In this example, we are accessing the `name` attribute of the Student object stored in the variable `jane`.

We can also treat those attributes just like any other variable, so we can assign a value to them as shown in this line of code.

So, we can easily add code to change any of the attributes of the student stored in `jane`.

Finally, we can access any of the methods in the Student object stored in `jane` in the same way. At the bottom of this example, we can see code calling the `birthday()` and `grade()` methods on that object.

As we continue in this module, we'll see more and more examples of instantiating objects based on our classes. By the end of this module, it should be a very familiar process.

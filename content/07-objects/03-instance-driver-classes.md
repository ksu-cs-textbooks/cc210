---
title: "Instance & Driver Classes"
pre: "3. "
weight: 30
---

Thus far in this course we have always had just one class, and in most cases one method.  So, while we have been following some object-oriented conventions like starting in `main()`, our designs have not followed an object-oriented programming paradigm.  This was deliberate, as the first few modules are necessary to cover the basics of program control.

We will begin bending our designs toward object-oriented programming with this module by introducing **instance** and **driver** classes.  The instance class holds certain data and all the methods to access and manipulate that data.  The driver class (typically only a `main()` method) holds the logic for how and when to use the data.  The driver generally only has indirect accesses to the instance's data through its methods[^1]

[^1]: this restriction is relaxed in this tutorial.

![Driver instance image](/images/07-object/driver_instance.png)

One of the things that makes OOP so powerful is this simple driver-instance idea can be used to model fairly complex real-world things.  For example when you use a web browser for research.  You act as the driver, you know how to uses the browser and the information you want.  The browser knows how to interact with the internet and all the little details to fetch and display information.

![Real world driver instance example](/images/07-object/student_browser.png)



---
title: "Java Methods"
pre: "4.J. "
weight: 40
hidden: true
date: 2019-09-24T00:00:26-05:00
---

{{< youtube t5Ehg2bjwlI >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Now that our classes contain attributes, the next thing we can add are the methods. For example, the Student class contains two methods: `birthday()` and `grade()`.

Let's start by adding the `birthday()` method. A method is just a function inside of a class, so we'll need to give it a return type, a name, and then parentheses containing the parameters followed by a set of curly braces.

Inside of the birthday method, we'll add the code that should be executed when that method is called. For a student's birthday, we'll just add 1 to the student's age.

However, since the age is a class attribute instead of a variable inside of the `birthday()` method, we'll need to use the `this` keyword, followed by a period, in front of the variable `age`. The `this` keyword simply refers to the current object, and helps us know that we are referring to the `age` attribute in the class. We'll see why that is important in the next method.

The `grade()` method is a bit more complex, since it accepts several parameters. We can refer to the UML diagram to find the names and types of each parameter.

Inside of the `grade()` method, we'll need to recalculate the GPA. So, first we'll need to figure out how many grade points the student has by multiplying the student's GPA by the number of credits. Remember, the GPA stands for "grade point average", which is the number of grade points divided by the number of credits, so to find the number of grade points we can just reverse that process.

However, since the GPA is a floating-point number, we may have to convert it to an integer, since grade points should be a whole number. It is tempting to just cast it to an integer, but what if we get a result such as 26.9999 due to floating-point error? Instead, we'll want to round that value to convert it to an integer, so we can use the `Math.round()` method to do just that. We'll also need to remember to import the `Math` library at the top of the class.

After that, we can simply update the number of credits and the grade points with the attributes given as parameters to this method. Notice that we have a parameter named `credits` as well as a class attribute named `credits`. Because of that, it is important to use the `this` keyword when referring to the class attribute, since any reference to `credits` without it will be assumed to be the parameter instead.

Finally, we can divide the updated number of grade points by the new number of credits to update the student's GPA and store it back in the class attribute for GPA.

There we go! We've now added some methods to our class. See if you can do the same for the Teacher class.

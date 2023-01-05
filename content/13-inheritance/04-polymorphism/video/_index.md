---
title: "Polymorphism"
pre: "2. "
weight: 20
hidden: true
date: 2019-11-03T00:00:26-05:00
---

{{< youtube ZIIMC9LNvZY >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

One of the most powerful aspects of using inheritance in our object-oriented programs is the ability to use polymorphism. Most programmers struggle to understand polymorphism at first, and even many experienced programmers would struggle to provide a quick and easy definition of polymorphism. It is one of those things that you have to work with a bit to understand fully. Let's dive in and see how it works.

Recall that we can think of variables as a box that we can use to store data. Variables have a data type, which tells us what type of data is stored in the box. Some languages, such as Java, require us to declare the data type of the variable when we declare it. Other languages, such as Python, infer the data type of the variable based on what we store in it. For this example, we'll assume that we are declaring the type of each variable before we store it.

Let's declare that this box can only store a person. So, that means we can definitely store an object instantiated from the Person class in it.

Likewise, if we declare that the box should store a teacher, we can definitely store a Teacher object into the box.

However, the power of polymorphism appears when we try to store a teacher object in a box that is declared to store a person. Will this work?

Indeed it will! If you think about it, it makes sense. A teacher is a _type_ of person, so if the box can store a person, it should also be able to store a teacher as well.

Put another way, if we say the box should contain a mammal, we could put dogs, cats, mice, and even humans in the box. Since each one is a mammal, we aren't violating the rules of the box.

Similarly, we can put a student object into a box that stores a person.

What if we try to store that same student in a box that should store objects of the Teacher data type. Will that work?

Nope! Since a student is not a type of a teacher, we can't store that object in this box.

Likewise, we can't store an object instantiated from the Person class in a teacher. This may seem a bit confusing, but we can rely on a statement from formal logic to help explain it. "All Teachers are People, but not all People are Teachers". Since we can't be sure that the Person object is a teacher, we can't store it directly in a box for a teacher.

As we'll learn later in this module, there are some very helpful methods we can use in our programming languages to determine which objects are compatible with different data types, and even convert objects between compatible data types if needed.

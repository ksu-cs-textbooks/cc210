---
title: "Software Design Patterns"
pre: "2. "
weight: 20
---

So, what does the design of door handles have to do with software? As it turns out, the concept of designing objects that are common, familiar, and easy to use and understand without lots of instruction is very similar to designing software. When we build software, we should try to structure it in a way that is easy for other developers to use and understand through the use of common, familiar, and easy-to-use _software design patterns_.

## What is a Software Design Pattern?

A [_software design pattern_](https://en.wikipedia.org/wiki/Software_design_pattern) is a commonly used structure for building a computer program, implementing a particular feature, or solving a common problem in software. These patterns are designed to be easily understood by developers, and are built in such a way that they can be reused over and over again in many different pieces of software. 

One common example is the [_adapter_](https://en.wikipedia.org/wiki/Adapter_pattern) or _wrapper_ design pattern. Suppose we have a class library that performs a particular action, such as managing a list of users. So, all of the methods use the term `user` in the name, such as `add_user()`, `delete_user()`, and more. What if we need to keep a list of players instead? We could simply build a class that inherits from that library, and include our own methods such as `add_player()` and `delete_player()`. In our version of the class, those methods simply call the `add_user()` and `delete_user()` methods of the parent class, effectively _wrapping_ them with new names. 

We can almost think of software design patterns as "building blocks" that we can use to build larger pieces of software. By using blocks that all developers would be familiar with, we can make our software much easier to understand and even maintain down the road. In addition, many of these design patterns represent the state-of-the-art method for solving a particular problem or implementing a feature. Why reinvent the wheel when the solution is already there?


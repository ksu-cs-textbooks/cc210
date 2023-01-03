---
title: "Exceptions Happen"
pre: "1. "
weight: 10
---

A good computer program should always run properly and produce the desired output. That is the whole point of writing code such that a computer can follow those instructions perfectly, with unerring accuracy and unrivaled speed. 

However, the real world, and the people that occupy it, is anything but perfect. Computers can crash, users can provide faulty input, and even the best programmers can create code that doesn't work exactly as intended. So, we need to have another tool in our arsenal of skills to help us deal with these issues in our programs.

When a computer program runs into a problem, we call that an _exception_. We most commonly use the word exception to indicate that something doesn't fit in a particular category or follow a rule, as in "we usually don't allow students in the faculty lounge, but I'll make an exception for you." 

We can think of an _exception_ in a computer program in a similar way. It is a program that has failed to follow a particular rule for some reason. Thankfully, we can write special code called _exception handlers_ into our programs to _handle_ these exceptions, without causing the program to stop running. In fact, many modern pieces of software may handle large numbers of exceptions each time they execute, allowing the program to continue to operate even when the user or the system isn't cooperating. 
---
title: "Exceptions vs. Errors"
pre: "2. "
weight: 20
---

Since Python is an interpreted language, it can be hard to tell the difference between _exceptions_ and _errors_. So, let's take a minute to review those two terms and what they mean. 

## Exceptions

An _exception_ is any issue encountered while executing a program that can be resolved within the program itself. Typically most exceptions come from incorrect user input, but they can be caused by other issues as well. However, just because an exception can be resolved by the program does not automatically mean that the program does, or must, include a handler for that exception. It just means that it could handle the exception, if the developer included the appropriate handler and code. 

## Errors

As discussed before, _errors_ are a special type of exception that cannot be easily handled by the program. These are usually due to issues in the underlying operating system or problems in the code itself. The Python interpreter may return errors such as SyntaxError or IndentationError relating to issues with the code, but it also may return errors such as SystemError or OSError if it encounters a problem that it cannot easily resolve. 



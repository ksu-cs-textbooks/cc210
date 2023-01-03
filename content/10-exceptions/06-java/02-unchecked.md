---
title: "Checked vs. Unchecked Exceptions"
pre: "2. "
weight: 20
---

Beyond the difference between exceptions and errors we've already discussed, Java also makes a distinction between two types of exceptions, _checked_ exceptions and _unchecked_ exceptions. Let's look more closely at each of these groups below. 

## Checked Exceptions

A _checked exception_ is detected by the Java compiler. When it detects a checked exception, the compiler then looks to see if the exception will be detected and handled within the code. If not, it will then check to see if the method containing that code includes a `throws` clause[^1] at the end of the method declaration that includes this particular exception. If neither of those is the case, then the compiler will output an error and refuse to compile the code. So, the developer must add one of these two things to the code in order for the compiler to be satisfied. 

[^1]: `throws` is a keyword in Java. It is only used to tell the compiler to ignore the lack of a handler for the checked exception

{{% notice info "Unchecked Exceptions at Compile Time" %}}

```tex
error: unreported exception someException; must be caught or declared to be thrown
```
If you get this type of message from the compiler, you have 2 choices.
1. Add `throws someException` to the signature line<br>`public void someMethod() throws someException {}`
1. Handle the exception with a try-catch block (discussed in this module)

In this class you will generally handle the exception.

{{% /notice %}}

## Unchecked Exceptions

An _unchecked exception_ is one that is not detected by the Java compiler. These are exceptions that can occur at runtime, but would be difficult or impossible to detect when compiling the code. However, in many cases they can easily be detected or prevented from within the program itself. So, the compiler does not require us to add code to either handle those exceptions or declare them to be thrown in to our method declaration. 

An ArithmeticException is a good example of an unchecked exception. Any division operation could result in an ArithmeticException, but the compiler does not require us to add additional code to handle that exception or declare it to be thrown. However, it is still good practice to either detect and handle this error, or use code or assertions to prevent it from occurring in the first place. 

## Errors

As discussed before, _errors_ are a special type of exception that cannot be easily handled by the program. These are usually due to issues in the underlying operating system, and typically cause the program to crash.  

### References

* [Checked vs Unchecked Exceptions in Java](https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/) from GeeksforGeeks
* [Unchecked Exceptions - The Controversy](https://docs.oracle.com/javase/tutorial/essential/exceptions/runtime.html) from Oracle
* [Errors vs Exceptions in Java](https://www.geeksforgeeks.org/errors-v-s-exceptions-in-java/) from GeeksforGeeks

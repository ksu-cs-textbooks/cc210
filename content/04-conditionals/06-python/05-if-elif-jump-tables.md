---
title: "If-Elif Jump Tables"
pre: "5. "
weight: 50
---

Many programming languages include a special type of conditional construct, called a **Switch Statement**. It allows the computer to select a branch directly based on the value of a variable. So, instead of building many inline **If-Else If-Else** statements, the code uses a single **Switch Statement** instead, with a number of cases that represent each possible value of the variable and the associated block of code that should be executed. **Switch Statements** are included in C, Java, and many other languages. 

Python does not include a **Switch Statement** construct. Since Python is not a compiled language, it cannot make use of the structure of a **Switch Statement** to optimize the generated machine code. Instead, we should just use the inline **If-Else If-Else** structure found on the previous page. 

{{% notice info "Communicating Mutual Exclusion" %}}

It should be obvious that only one branch of an **If-Else If-Else** will ever be executed; that is the branches are mutually exclusive.  It is a excellent practice always use **If-Else If-Else** whenever you know the logic should be exclusive.  Consider the  Goldilocks Porridge Temperature Tester.

```text 
if isTooHot: 
     print ("porridge is too hot")
if isTooCold:
     print ("porridge is not hot enough")
if isJustRight:
      print ("porridge is perfect")
```
A future reader of the program, unfamiliar with the children's tale, would see there are 3 boolean variables (isTooHot, isTooCold, isJustRight) and, depending on their values up to 3-lines might get printed.  But if instead the program was

```text 
if isTooHot: 
     print ("porridge is too hot")
elif isTooCold:
     print ("porridge is not hot enough")
elif isJustRight:
      print ("porridge is perfect")
```
the future reader would know that only one line should ever be printed.

{{% /notice %}}
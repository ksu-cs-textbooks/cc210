---
title: "Else Clause"
pre: "4. "
weight: 40
---

Python is non standard in many ways. One of the features of Python is the ability to add an **Else** clause at the end of loops. The **Else** clause on a loop can be used to detect certain situations related to working with a loop.

## While Else

On a **While** loop, the **Else** clause will be executed when the Boolean expression of the **While** loop is found to be `False`. However, it _will not_ execute if the loop is terminated using a `break` statement. 

Here's a quick example of using an **Else** clause with a **While** loop:

```python
number = 11
factor = 2
while factor < number:
  if number % factor == 0:
    print("Not Prime!")
    break
  factor += 1
else:
  print("Prime!")
```

This program can be used to determine if the variable `number` is a prime number. It does so by checking to see if it is equally divisible by any number starting at $2$ up to its own value using the modulo operator. If it is evenly divisible, the program will print `Not Prime!` and immediately break from the loop.

However, if the loop runs its course and terminates because `factor < number` is no longer `True`, then the program will run the **Else** clause after the **While** loop. Notice that the `else` keyword is indented at the same level as the `while` keyword, showing that it is attached to the **While** loop and not the **If-Then** statement. In this case, we didn't find a single factor that can evenly divide the number, so it must be a prime number. 

{{% notice info "Use of the While-Else Construct" %}}

This is one of those places where Python is very not standard.  The vast majority of non-Python programmers are not going to know how to interpret this code.  If you are writing code only for Python readers, or to impress a Pythonista, use it.  But a more standard way of accomplishing the same goal is:

```python
number = 11
factor = 2
prime = true
while (factor < number) and prime:
  if number % factor == 0:
    prime = False
  factor += 1
if prime:
  print("Prime!")
else:
  print("Not Prime!")
```

{{% /notice %}}
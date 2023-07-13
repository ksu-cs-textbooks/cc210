---
title: "Loop Control"
pre: "5. "
weight: 50
---

{{% youtube iHSvRufI4fY %}}

[Video Materials]({{<relref "./video">}})

Once our code is inside of a loop, sometimes we might find situations where we need to either stop looping immediately, or perhaps start the loop over again. Thankfully, most programming languages include two special keywords that can be used in those situations.

## Break

The first of these keywords, `break`, is used to immediately exit a loop from within. The program will immediately jump to the first line of code below the loop and continue executing from there. This flowchart gives a good example of what this might look like:

![Break Flowchart](/images/05-loop/5.5.break.png)

This program will accept an integer as input, and then print the smallest positive integer that is not a factor of the given input. Let's walk through this program and see if we can figure out how it works.

For this example, let's say the user has chosen `30` as the input. At the beginning, the program will set `i = 1`. Then, it will evaluate the Boolean expression `true` to determine if it should enter the **While** loop. Since this expression is always `true`, the loop will be repeated continuously, unless we use the `break` keyword to exit the loop. These loops are sometimes referred to as _infinite loops_, and can be very dangerous to use unless we are very careful.

Inside the loop, it will evaluate `x % i != 0` as part of an **If** statement. In this case, `30 % 1 != 0` is `false`, so the loop will continue on the False branch of the statement and increment `i`. 

Then, it will loop around again and go right back to the **If** statement, which will evaluate `30 % 2 != 0` to `false` as well, so it will once again increment `i`.

This process will continue until `i = 4`, at which point `30 % 4 != 0` is `true`. In that case, it will follow the True branch of the **If** statement, which will print `4` as output. Then, the next statement is a `break` keyword. As soon as the code reaches that statement, it will _break_ out of the loop and continue to the next line of code below the loop. In this case, there is no more code, so the program will just terminate.

The `break` keyword is very important when working with loops, as it allows us to perform additional checks inside of the loop using **If** statements to determine if the loop should stop at any point. 

## Continue

The other of these keywords, `continue`, is used to stop executing the current iteration of the loop, but instead will return to the beginning of the loop and start the process over again with the current variables. Here's a flowchart for a program that uses the `continue` keyword:

![Continue Flowchart](/images/05-loop/5.5.continue.png)

This program is the inverse of the previous program. It will print all positive numbers that are factors of the given input. In this case, it was built using a **For** loop instead of a **While** loop. Let's walk through this program and see how it works.

In this example, we'll assume the user has chosen `8` as the input. So, the program will start with `i = 1` and evaluate the Boolean expression `x % i != 0`. In this case, that expression is `8 % 1 != 0`, which is `false`. So, the program will output `1` and loop back to the beginning. 

The same process applies for the second iteration, where `i = 2`. Since `8 % 2 != 0` is `false`, the program will also output `2` and loop.

However, when `i = 3`, something different happens. In this case, `8 % 3 != 0` evaluates to `true`, since {{< math >}}$ 8 ${{< /math >}} is not equally divisible by {{< math >}}$ 3 ${{< /math >}}. Inside of the **If-Then** statement is the keyword `continue`, which just tells the loop to stop executing the current iteration and go back to the beginning of the loop. Since this loop is a **For** loop, the value of `i` will be updated to `4`, and the loop will begin again.

Continuing through the entire program, we'll see that it outputs `1`, `2`, `4`, and `8`, while the other numbers are skipped. This is exactly the expected output.

In many cases, the `continue` keyword is used along with an **If** statement to show which iterations or variable values should be ignored or skipped in a loop.

{{% notice info "Using Break & Continue" %}}

There are some areas of programming, such as video games that use a "game loop", as well as a few programming languages, where `break` and `continue` are commonly used. However, as a general rule, it is not recommended to use `break` or `continue` very often in your code, since it can make understanding and following the code much more complex. Instead, try to use the loop conditions to determine when a loop should terminate, and rewrite your code if needed. 

{{% /notice %}}


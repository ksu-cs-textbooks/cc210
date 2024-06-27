---
title: "Loop Control"
pre: "3. "
weight: 30
date: 2019-02-08T00:00:26-05:00
hidden: true
---

{{< youtube iHSvRufI4fY >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Most programming languages also include specific keywords to help control how loops function from inside. Let's take a look at the two common keywords, break and continue, and see how they work.

First, let's examine this flowchart, which uses the break keyword. This program should find the smallest positive integer that is not a factor of the input from the user.

So, in this example, let's assume the user inputs 30, which will be stored in variable `x`. Since we are using a while loop, we'll also create an iterator variable `i`, which will help us keep track of where we are in the loop.

Finally, this loop is a special type of loop, known as an "infinite loop" or sometimes a "while true" loop, since it will run continuously unless we use the special `break` keyword to stop it.

Inside of the loop, we find an If-Then statement that checks to see if the value in `x` is not equally divisible by `i`. So, since 30 is indeed equally divisible by 1, this evaluates to false, so we follow the false branch. On that branch, we just increment the value of `i` to 2, and loop back to the beginning.

We'll now see that 30 is equally divisible by 2, so we'll increment `i` again to 3 and repeat.

We'll do the same again for 3, incrementing `i` to 4.

At this point, we'll now see that 30 is NOT equally divisible by 4, so we'll follow the true branch and output that value to the screen. Finally we reach the `break` keyword, which tells us to "break" out of the loop and continue the program. In this case, the program terminates, and we see that it indeed worked as expected.

Next, let's look at a program that uses the other keyword, the `continue` keyword. This program should output all possible factors of the number input by the user. Let's walk through it.

First, we'll accept input from the user and store it in the variable `x`. In this case, let's assume the user input the value 8.

We're also using a for loop for this example, so we'll initialize the iterator variable `i` to 1.

Inside of the loop, we'll check to see if `x` is not equally divisible by `i`. If that evaluates to true, we'll go inside of the If-Then statement. However, since 8 is indeed equally divisible by 1, that evaluates to false, so we follow the false branch. In that case, we'll output 1 and go back to the top of the loop.

The for loop will then update the value of `i` to 2, and we'll reenter the loop. Inside of the loop, we see that 8 is equally divisible by 2, so we'll output that and loop back to the beginning.

`i` will be updated to 3. Now, we see that 8 is not equally divisible by 3. So, we'll follow the True branch of the If-Then statement. In that branch we see the keyword `continue`, which tells us to simply "continue" executing the loop back at the beginning. So, we'll jump back to the top and update `i` to 4.

Since 8 is divisible by 4, we'll output that value and repeat.

For the values 5, 6, and 7, we know that 8 is not divisible by either of those values, so we'll reach the `continue` keyword each time and restart the loop.

Finally, when `i` is 8, we'll output 8.

That exhausts the items in the list, so we'll exit the loop and terminate the program.

There we go! We've now covered both the `break` and `continue` keywords. Of course, it is possible to write each of these programs without using these keywords. But, you may find at times that these keywords make your code easier to read and follow, so feel free to use them as needed.

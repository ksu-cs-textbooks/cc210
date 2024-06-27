---
title: "Iteration"
pre: "2. "
weight: 20
date: 2019-02-21T00:00:26-05:00
hidden: true
---

{{< youtube 11R9oFjc008 >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

Let's walk through a quick example showing how we can use for loops to iterate over an array once to fill it with data from the user, then again to perform an operation on that data.

On this slide is the same flowchart that is in the textbook. I've changed the layout just a bit so that it fits on these slides better, but otherwise it is exactly the same.

When we start the program, we first ask the user how many items will be stored in the array. This is important here, since most programming languages require us to know the size of the array before we start putting data into it. So, we'll accept that input from the user, in this case 3, and store it in `x`.

Then, we can use that variable to create an array named `a` with size 3. Each language does this differently, so I'm using a simplified syntax here in this flowchart.

Next, we'll reach this for loop. Here, you'll notice that we are using `i` as our iterator variable, and it will be given all values starting at 0 up to, but not including, `x`. I'm using a notation from mathematics for a range of numbers. The square bracket on the left indicates that 0 is included, but the parenthesis on the right shows that `x` is NOT included in the range. Pretty neat, right? This is exactly how Python's `range` function works, by the way.

So, we'll set `i` to 0, and then enter the loop. Once inside, we'll get input from our user, store that input in `y`, and then place that input in the first element of the array `a`, which has the index 0. So, if the user inputs 2, we'll store 2 in `y`, and then place 2 in at index 0, indicated by `i`, in the array named `a`.

The loop will then repeat. Notice that the variable `y` is not visible here. This is because we declared it inside of the loop. So, we need to make sure that we understand that the variable may not be available here, depending on which langauge we are using.

Since we still have more values for `i`, we'll set `i` to 1 and enter the loop again.

This time, the user will input 4, which is stored in both `y` and the second element of `a`, at index 1.

We'll loop around once again, set `i` to 2, then get one more input from the user. This time the user inputs 6, so we'll store that in the appropriate places.

At this point, we are all out of items in our range, so we'll exit the loop and move on to the next part of the program.

So, we'll set the value of the `sum` variable to 0, and then reach our next for loop.

This for loop uses a slightly different syntax than we've seen before. Instead of using a range or sequence of numbers, we can use the array itself as the source for our iterator variable. This type of for loop is sometimes referred to as a **for each** or **enhanced for** loop, depending on the language.

So, in this case, we'll set the value of the variable `j` to the first item in the array named `a`, which in this case is 2.

Once inside the loop, we'll simply add that value to `sum` before repeating the loop.

Now, we'll get the second item in `a`, which is 4, and store it in `j`.

Then, we'll add that value to `sum`.

Finally, we'll grab the last value in `a`, store it in `j`, and then add it to `sum`.

Once we've run out of items in `a`, this loop will terminate and we'll move on to the next part of the program.

Here, we'll just print out the value of sum, which should be 12.

This flowchart gives us a quick overview of one program structure that we could use in our programs to create an array, populate it with data, and then perform operations on that data. This program structure is used quite often when working with arrays of data, so we'll definitely see it again in this chapter.

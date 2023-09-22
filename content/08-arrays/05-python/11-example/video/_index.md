---
title: "Python Example"
pre: "3.P. "
weight: 31
date: 2019-02-21T00:00:26-05:00
hidden: true
---

{{< youtube KYquHPtkEg8 >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

Let's walk through the example on this page to see how we can build a program using lists and loops to calculate weighted scores.

As always, we need to first start with our standard program skeleton that allows us to read input from the user. We've seen this code several times before, so we won't spend any time discussing it here. We'll place the code for this example where the highlighted comment is here.

First, we need to handle the input. The problem statement says that we should first accept an integer giving the number of scores we'll be storing. So, we'll read an integer from input and store it in a variable.

Then, we'll need to verify that the input is valid. So, if the input is not greater than 0, we should print an error message to the screen.

If it is greater than 0, we can use that input to create two new lists, one to store the scores and another to store the weights. Notice that we are using two different lists here! This is because we cannot store different data types in the same list. So, we'll create one list that stores integers for the scores, and another for the weights. Both of them have the same size.

Next, we'll need to fill those lists with input from the user. So, we'll need a standard for loop that runs once for each input, and then we can read an integer into the scores list and a floating point number into the weights list.

Once we have our data, we need to verify that the weights all sum to 1.0. So, we can use another for loop to do this. Here, we are using a **for each** loop to iterate over the items in the weights list. Inside the loop, we'll just sum them up and make sure the result is equal to 1.0. If not, we'll print an error message to the screen.

If the weights check out, we can then calculate the score. Here, we are not using a **for each** loop, since it would only allow us to iterate through one list at a time. Instead, we'll end up using a standard for loop, and use the iterator variable `j` as our list index in each list. Inside of the loop, we'll multiply the score and the weight and then add that result to the total score.

Once that is done, we'll just print the score to the screen.

There we go! While the program may seem pretty complex at first, if we break it down into each step, we see that this program is really just comprised of a few parts, most of which we've already seen before in this chapter. So, don't let a big program scare you! Just break it down into smaller parts and work on it a little bit at a time!

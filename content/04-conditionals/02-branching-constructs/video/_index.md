---
title: "Rock Paper Scissors"
pre: "1. "
weight: 10
date: 2019-02-07T10:53:26-05:00
hidden: true
---

{{< youtube B-P4hS0a4tg >}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

#### Video Script

This chapter introduces conditional statements, which allow us to create branches of code in our program that can be executed based on the value of any Boolean expression we can create.

To really understand how to use branching in our programs, let's walk through a couple of examples.

This flowchart represents a program designed to play the classic "Rock, Paper, Scissors" game that you're probably familiar with from childhood.

To run this program, we start at the Start node at the top. The first box asks the user for input, and stores it in the variable p1. For this example, let's assume the first player picks "rock".

Then, we'll reach another input node, and the second player can input a value. Let's use paper.

Not, we reach our first decision node. Notice that each of these diamond-shaped nodes has not one, but two arrows coming off of it. The one labelled True is used when the Boolean expression in the node evaluates to True. Otherwise, we follow the arrow labelled False.

This node contains the Boolean expression p1 == p2, so we are checking to see if the two users input the same value. Since this expression evaluates to False, we'll follow the False branch to the left.

The next decision node asks if player 1 chose rock. Since that evaluates to True, we'll go to the left and follow the True branch.

Similarly, the next node asks if the second player chose paper. That is also True, so once again we'll move to the right.

Now, we've reached an output node, so our program will print "p2 wins" to the screen. In the rules of the game, we know that "paper covers rock" so player 2 does indeed win.

Finally, our program reaches the End node, and the program terminates.

Let's do one more. This time, we'll have player 1 choose scissors, and player 2 will still choose paper.

In this case, once again player 1 and player 2 did not choose the same input, so this first decision node is false, and we'll move left.

Next, we check to see if player 1 chose rock. That is false, so we go left again.

After that, we check to see if player 1 chose paper. That is also false, so we continue to the left.

At this point, we know that player 1 did not choose rock or paper. So, as long as we assume that player 1 chose a valid value, we can know that player 1 must have chosen scissors instead. In a later chapter, we'll discuss how to make sure that the users have indeed input a valid value. For now, we'll just assume that is the case.

So, now that we've determined player 1 has input scissors, we can then determine what player 2 chose. Once again, we know that player 2 couldn't have also input scissors, since that would be covered by the very first decision node above. So, this decision node will check if player 2 input rock. Since that isn't true, we go to the left one final time.

At this point, based on our previous assumptions, we know that player 1 must have entered scissors since we already determined that it wasn't rock or paper. Similarly, we know that player 2 didn't input rock, and also didn't input the same thing that player 1 did. So, that leaves paper for player 2. Therefore, since player 1 chose scissors and player 2 input paper, we can say that player 1 wins since "scissors cuts paper". We can output that to the screen, and then our program terminates.

These flowcharts provide a very handy way to learn how to deal with these decision nodes, or conditional statements, in our code. Later on, we'll use these flowcharts again to learn about how to deal with loops, or repeated code segments.

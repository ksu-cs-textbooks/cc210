---
title: "Loop Control"
pre: "11. "
weight: 110
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

There are some application areas (for example game-loops) and some high-level programming languages where "Break" and "Continue" are common place; but these are niche areas.  There are also some safety and security critical application areas which will not allow their use, as they make guaranteeing a system's behavior exponentially more complex--these are also niche areas.  As with all things computer science, you will find on-line threads both condemning and advocating their use.  

As a general rule, if you find you are using them often, you may be choosing the wrong construct, i.e. a **For** when you should be using a **While**.

In any event, if you have a loop with more than one "break"/"continue" you should consider re-writing the code with an eye toward making your intent more clear to future readers.  Correctness and clarity are hallmarks of well written code.

{{% /notice %}}

## The Game Loop[^1]

[^1]: See K-State CC 110, Lab 4, Lavezzi 2021

In many situations, loops will depend on user input.  A _game loop_ repeats the core functions of a game or program over and over, often including collecting input from the user. Game loops are often written `REPEAT WHILE (TRUE){}`, with break statements for winning and losing conditions.  Let's look at a basic guessing game as an example.

```tex
num <- RANDOM (0, 100)
DISPLAY(NUM) # Remove line after testing
REPEAT WHILE (TRUE){

   guess <- INPUT()
   IF (guess = num) {
       BREAK
   }
   ELSE{
      IF (guess > num){
          DISPLAY("Your number is too high!")
      }
      ELSE{
          DISPLAY("Your number is too low!")
      }
}
DISPLAY("You guessed it right!")
```

```tex
40
Please guess a number between 0 and 100: 50
Your number is too high!
Please guess a number between 0 and 100: 40
You guessed it right!
```

The code above is the core functionality of a simple guessing game without a loop where the user enters the number 40^[We print out 'num' so we know what is is for testing, you would of course delete the print out in production code.].  In pseudo code, we create a random integer between a and b by calling the `RANDOM(a,b)` function.  `RANDOM(1,3)` has an equal chance of returning `1`,`2`, or `3`.  Then we can get a guess from the user and see if they guessed right, or if we need to give them a hint.   This logic is wrapped in a loop allowing the player to guess until they have won.

Note is is never necessary to use `REPEAT WHILE (TRUE){}`.  The program below is essentially the same and avoids this construct.


```tex
num <- RANDOM (0, 100)
DISPLAY(NUM) # Remove line after testing
guess <- num -1
REPEAT WHILE (guess ≠ num){

   guess <- INPUT()
   IF (guess > num){
       DISPLAY("Your number is too high!")
   }
   ELSE{
       IF (guess < num){
           DISPLAY("Your number is too low!")
       } 
   }
}
DISPLAY("You guessed it right!")
```


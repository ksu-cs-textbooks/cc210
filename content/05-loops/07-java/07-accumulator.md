---
title: "Accumulator Pattern"
pre: "7. "
weight: 70
---

One common use for loops is the **accumulator pattern**. An accumulator simply computes some values based on a large amount of data, such as the sum, maximum, minimum, average, or count. In programming, a **pattern** is simply a common structure that is used to solve a recurring problem in code. Since many programs end up needing a loop that acts an accumulator, we've developed a common pattern that can be used in our code to solve this problem.

The simplest example of the accumulator pattern is a program that will sum up a set of values. Consider this code:

```java
import java.util.Scanner;

public class Accumulator {

    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);

        // Initialize accumulator variables
        int sum = 0;

        // Read and parse input
        while(scanner.hasNextLine()){
            String input = scanner.nextLine();
            if (input.trim().length() == 0){
                break;
            }
            int x = Integer.parseInt(input);

            // Update accumulator variables
            sum += x;
        }

        // Display results
        System.out.println("The sum of these values is " + sum);
    }
}
```

In this example, we see the general structure for the accumulator pattern:

* Before the loop, we initialize any accumulator variables to their default values. Since we are computing the sum, we should start at 0. However, when computing other values, such as the product, we may need to initialize these values to 1, -1, or some other value. It doesn't _always_ make sense to start at 0.
* Inside of the loop, we read the input and parse it. Then, we will update the accumulator variables before repeating the loop. 
  * Many times we also include a conditional statement here and only update the variables if the Boolean condition is `true`. For example, we could easily modify this program to only sum up the even values using a conditional statement.
* After the loop ends, we can then display the accumulated results. In some cases, such as when we are computing the average of a list of values, we may have to perform some final calculations here before displaying the result.

We'll see this pattern appear many times in our programs from this point onward, so it is helpful to make note of it and observe when it is used in practice.

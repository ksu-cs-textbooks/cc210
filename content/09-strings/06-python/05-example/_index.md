---
title: "A Worked Example"
pre: "5. "
weight: 50
---

{{< youtube X2zeNRjT0l8  >}}

[Video Materials]({{% relref "./video" %}})

Now that we've explored all of the different ways we can use strings in our programs, let's walk through a worked example to see how we would go about building a useful program that uses everything we've learned so far. 

## Problem Statement

Consider the following problem statement:

> Write a program that will calculate weighted grades for students in a college course. The input will be given in a comma-delimited format. The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.

> Each subsequent line of input will contain information for a student. The first entry on that line will contain that student's name. The rest of the line will contain that student's scores on each assignment as an integer value, separated by commas. Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal. 

> It is guaranteed that at least two lines of input will be provided, the first containing the weights and at least one additional line containing data for a student. In addition, it is guaranteed that each line of input will contain the same number of parts. 

> The program should output the student's name, followed by a colon, and a space, and then the student's score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point. 

Complete your solution to this example in `Example.py` as a driver class (only one method (`main`)), which is open to the left. 

## Sample Inputs & Outputs

Here's an example of the expected input for the program:

```tex
Name,0.125,0.125,0.25,0.50
StudentA,75,80,85,90
StudentB,5,15,75,20
StudentC,85,90,70,75
```

Here is the correct output for that input:

```tex
StudentA: 85.63
StudentB: 31.25
StudentC: 76.88
```
##  Think and Design Before Coding

Start by sketching the control flow, what kind of loops are appropriate, what variables and lists will be necessary?   What packages will need to be imported?

## Handling Input

Next, start with our standard program skeleton for driver classes that we've worked with previously in this course:

```python
import sys

class Example:
    
    @classmethod
    def main(cls, args):
        reader = sys.stdin
        
        
if __name__ == "__main__":
    Example.main(sys.argv)
```

For the rest of this example, we'll look at a smaller portion of the code. That code can be placed in `main()`'s body. 

## Parsing Weights

First, we'll need to parse the weights provided on the first line of the input. So, we can begin by reading that line of input:

```python
weightLine = reader.readline()
```

Then, we can tokenize (separate) that line into its individual parts using the `split()` method:

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")
```

Once we've done that, we can populate a list of floating point numbers containing the weights. To do this, we know that the number of weights is one less than the size of the `weightParts` list. However, to make things simpler, we'll simply create a list with the same size and leave the first element blank. This will help us when we perform the second step below.

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")

weights = []
weights.append(0.0)
```

Next, we can iterate through the `weightParts` list, and parse each entry to a floating point value and store it in the `weights` list. In this case, we'll use a  **For** loop, but this time we'll start iterating at 1 instead of 0. In this way, we'll skip the first entry in `weightParts`, which cannot be converted to a floating point value.

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")

weights = []
weights.append(0.0)

for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
```

Inside of the **For** loop, we are simply converting each element of `weightParts` to a floating point value, and then storing the result in the corresponding element in `weights`.

Also, notice that we're using the length of `weightParts` in the range of this **For** loop. This helps us make sure we are reading all of the weights into the list correctly. 

## Parsing Each Student

Once we've read the weights, we can parse the data for each student, calculate the result, and print the output, all in a single step. 

First, since we are reading an unknown number of lines of input, we'll need to use a **For** loop. We saw this loop earlier in this chapter, when we learned about how to handle parsing input of an unknown length. 

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")

weights = []
weights.append(0.0)

for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
  
for line in reader:
  if not line or len(line.strip()) == 0:
    break
    
  # parse the input
```

Inside of that loop, once we've determined that we've indeed read a valid line of input, we can use the same `split()` method as before to split the input into parts:

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")

weights = []
weights.append(0.0)

for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
  
for line in reader:
  if not line or len(line.strip()) == 0:
    break
    
  parts = line.split(",")

```

Then, we want to calculate the student's final grade. So, once again, we'll create a sum variable and iterate through all of the parts. As before, we'll start the **For** loop at 1, just to skip the first element for now:

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")

weights = []
weights.append(0.0)

for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
  
for line in reader:
  if not line or len(line.strip()) == 0:
    break
    
  parts = line.split(",")
  
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])

```

Inside of the **For** loop, we'll multiply the weight of the assignment by the score. Since we don't need to store the integer value of each score, we can simply convert it to an integer and then directly use it in our expression. 

## Formatting Output

Finally, we'll need to provide our output as a formatted string. Since we want to make sure the output of the `totalScore` variable is exactly 5 characters wide, with 2 characters after the decimal point, we'll use the placeholder `{:5.2f}` in the format string:

```python
weightLine = reader.readline()
weightParts = weightLine.split(",")

weights = []
weights.append(0.0)

for i in range(1, len(weightParts)):
  weights.append(float(weightParts[i]))
  
for line in reader:
  if not line or len(line.strip()) == 0:
    break
    
  parts = line.split(",")
  
  totalScore = 0.0
  for j in range(1, len(parts)):
    totalScore += weights[j] * int(parts[j])
  
  print("{}: {:5.2f}".format(parts[0], totalScore))

```

In the output line, we are providing `"{}: {:5.2f}"` directly as a string literal, then using the `format()` method on that literal. In this way, we don't have to create a separate variable to store the format string, simplifying our code. Then, the first input is the first element in the `parts` list, which will contain the student's name. Finally, the last input is the `totalScore` variable, giving the student's total score. 

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}


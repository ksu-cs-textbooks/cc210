---
title: "A Worked Example"
pre: "11. "
weight: 110
---

{{% youtube KYquHPtkEg8 %}}

[Video Materials]({{<relref "./video">}})

Now that we've learned how to work with loops and lists, let's see if we can solve a more challenging problem using loops and lists.

## Problem Statement

For this example, let's build a program that matches the following problem statement:

> Write a program to calculate weighted grades for a student taking a course. The program should begin by accepting the student's name and a single positive integer as input, giving the number of assignments in the course. If the input is invalid, simply print "Invalid Input!" and terminate.   All input is from the keyboard.

> The program should accept the test scores, as ints between 0 and 100, and the test weights, in order, as floats between 0. and 1. The input pattern will be: test 1, test weight , test 2, test weight 2, ...

> If an out of range score or weight is input, the program should simply print "Invalid Input!" and terminate.  If too many test are entered, print "Invalid Input!" and terminate.

> The program should ensure that the total sum of the weights is equal to 1.0. If the weights do not add to 1.0, The program should print "Invalid Input!" and terminate.

> The program should print out the the student's final final score. For each assignment, multiply the score and the weight, and then add that value to the total score for the student. The print out should be of the form `<name> earned a ##.##` or `Trace earned a 78.86` .  Use `"{} earned a {:.2f}".format(<name>, <final_score>)` to create the string for printing.

## Class Diagram

We'll start by roughing out a Driver-Object class UML.  Since instances are about the data, lets put all the data and logic about the student and exams in a `Student` class. Next lets describe the methods which might be useful access and manipulate that data.

* The attributes would include a student's name, the number of exams and lists of their exam scores and and weights.

* The methods would include
    * a constructor that accepts as parameter's the name and number of tests.
    * a method to input a single tests score and weight, with a way to signal if some invalid input has happened
    * a method to check if the test weights sum to 1
    * a method to calculate the final score
    * a toString method that returns `<name> earned a ##.##`
    
Lets have the input method return True if everything with reading and storing the data goes ok, and False it any invalid data is used.

We'll run it with a driver class, which will:

* takes input for the name and number of tests
* creates a Student object
* Calls the appropriate methods the right number of times to 
    * enter the correct number of scores and weight
    * print out the final score as indicated above
* If any Student method indicates invalid input was sent, prints "Invalid Input!" and terminates the program


![Student-Driver UML](/images/08-array/Student_scores_uml.png)   


###  The Student Class

First, we'll need to build the skeleton of our class

```python
import sys
import math

class Student:
    
    def __init__(self, name, tests):
        pass
    
    def add_test(self, score, weight):
        pass
    
    def __sum_weights(self):
        pass
    
    def __calc_grade(self):
        pass
    
    def toString(self):
        pass
  ```

This class definition, will interpret without errors.  Each method has the correct signature and  this skeleton should pass any structure test.  As a side note, since Python is dynamically interpreted, it is possible to "pass" a structure's test and still return the wrong type of value.  For this reason, the return type of a method in PYTHON is tested as part of the method's functionality tests.   

Notice the `list <int>` in the UML.  The `<sterotype>` annotation is used to convey extra meaning.  In this case that we expect a list of integers. 


#### Start with `__init__()`

We know the constructor , `Student(name: string, num_tests: int)` on the UML, is the special function `__init__` in Python and it need to set up all the instance attributes, of which there are four.  Observe how all the names start with `__`.  This <i>mangles</i> the name, making it harder for classes other than `Student` to access the attribute.  In constructors, it is common for the parameter name to match the instance attribute name it is intended to fill.


```python
def __init__(self, name, tests):
    self.__name = name
    self.__num_tests = tests
    self.__test_scores = []
    self.__test_weights = []
```

Here we have chosen to initialize the two lists as an empty list (`[]`).

{{% notice warning "Test As You Go!" %}}

Test each method as you go.  Identifiers starting with `__` cannot be accessed[^1] outside of the class in which they are defined.  The following won't work

[^1]: Actually, Python does have a way to enable access, but is is considered bad style.

```python

##### end of class
if __name__ == "__main__":
    temp = Student("Mari", 4)
    print(temp.__name)
    print(temp.__num_tests)

```

It will generate an error very similar to `AttributeError: type object 'Student' has no attribute '__name'`.  Because the main-guard is out side the class definition, it cannot "see" the double underscore features.

What will work is

```python
    def __TEST(self):
        print(self.__name)
        print(self.__num_tests)

    @classmethod
    def main(cls, args):
        Student.__TEST()

##### end of class
if __name__ == "__main__":
    Student.main(sys.argv)) # 
```

Since the method `__TEST` is <b>inside</b> the class definition of `Student` it has access to all the double-underscored stuff.  Since the method `__TEST` is itself double-underscored, it must be called from a "visible" method i.e. `main()`.

{{% /notice %}}

#### Move to `add_test()`

First we need to check a few things when arriving in `add_test`.  We need to make sure the lists are not at the their stated capacity (`__num_tests`).  Then we need to ensure that the parameters are in range.  If we see a problem, which return False.

Assuming the parameters are, add them to the list.

Finally, if the weights-list is now full, we need to check that is sums to `1.0`.  We have a method, `__sum_weights()` which performs this check so we just call it.


```python
def add_test(self, score, weight):
    if len(self.__test_scores) < self.__num_tests:
        if (score < 0 or score > 100
            or weight <0. or weight > 1.):
            return False
        self.__test_scores.append(score)
        self.__test_weights.append(weight)
        if len(self.__test_weights) == self.__num_tests:
            if not self.__sum_weights():
                return False
        return True
    else:
        return False
```

Thus the method might get used like

```
IF (NOT <obj>.add_test(80, .25)) {
   DISPLAY(ERROR)
   EXIT
}
```
If there is a problem in processing the parameters, `add_tests()` returns False.  `NOT FALSE` is TRUE so we go into the IF-body, display an error then quit.

#### `__sum_weights()` 

Here we use an accumulator pattern and for-loop through the weights .  Recall that `float == float` is subject to representation errors.  We use `math.isclose(float,float)` which returns TRUE if the numbers are within a billionth (1E-9) of each other.

```python
sum = 0
for i in self.__test_weights:
    sum += i
return math.isclose(1., sum)
```
    
#### `__calc_grade()`

Here we use the accumulator pattern to sum up the contribution of each test (test_score[i] * test_weight[i]).  We can do this because we entered the scores ad weights in order: test_score[1] is matched with test_weights[1].  

This practice is called parallel-lists or parallel-array.  Each list has different type of data, but each index in the all lists the refer to the same thing.

```python
sum = 0.0   
for i in range(self.__num_tests):
    sum += self.__test_scores[i]*self.__test_weights[i]
return sum 
```


#### `toString()` ---> hereafter  `__str__()`

Here we use the given string `"{} earned a {:5.2f}".format(<name>, <final_score>)`.  We just return it.

```python
def toString(self):
    return "{} earned a {:.2f}".format(self.__name, self.calc_grade())  
```

<b>BUT</b> a `toString()` method is not very Pythonic.  Instead, <b>when we see a `toString()` we will implement `__str__()`.</b>  

```python
def __str__(self):
    return "{} earned a {:.2f}".format(self.__name, self.calc_grade()) 
```

The `__str__()` method is called whenever a piece of the program tries to convert the object into a string. 


`print(s.toString())` and `print(s)`  will produce the same results.
*   `s.toString()`  calls `s`'s `toString()`,  which returns a string, which Python knows how to print.  
*    Python does not know how to print a &lt;type Student&gt;, so it calls `str(s)`.  `str(s)` calls `__str__`, which returns a string, which Python knows how to `print`.

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}

## Driver Class

* takes input for the name and number of tests
* creates a Student object
* Calls the appropriate methods the right number of times to 
    * enter the correct number of scores and weight
    * print out the final score as indicated above
* If any Student method indicates invalid input was sent, prints "Invalid Input!" and terminates the program

Below is a shell we leave for you to complete.

```python
import sys
from Student import *

class Driver:
    
    @classmethod
    def main(cls, args):
        reader = 
        name = reader.readline().strip()
        n_test = 
        s = Student(name,n_test)
        for i in range():
            x = int()
            y = float()
            if not (s.add_test(x,y)):
                print("Invalid Input!")
                return
        print(s)
        
# main guard here

```

A sample run might look like

```text
~/workspace/python$ python3 Driver.py
bob 
2
100
.5
60
.5
bob earned a 81.00
```

{{% notice noiframe %}}

This content is presented in the course directly through Codio. Any references to interactive portions are only relevant for that interface. This content is included here as reference only. 

{{% /notice %}}






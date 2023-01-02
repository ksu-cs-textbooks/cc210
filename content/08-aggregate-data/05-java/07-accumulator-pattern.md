---
title: "Accumulator Pattern"
pre: "7. "
weight: 70
---

{{% youtube Ga_pktkY0Cg %}}

<!-- TODO Update Video -->

The accumulator pattern and its adaptations are very useful when you want to compile certain information about the elements (values) in an aggregate data collection.  The general pattern is 

```text
dataSet <- some aggregate data

accumulator <- initial value

FOR EACH item IN dataSet{

    IF (filtering condition){

 	accumulator <- accumulator + item
     }
}
```

*  Start with some aggregated data (`dataSet`)
*  Initialize your accumulator variable BEFORE the loop
*  * generally `1`, `0`, `""`, or and empty list/array
*  Loop through every element of the `dataSet`
*  * <em>Optionally</em> filter the elements
*  Update the accumulator for the element
*  AFTER the loop the accumulator variable holds the value(s) you want

To add up all the odd elements of an integer array, one might

```java
int[] dataSet = { 1, 2, 3, 4, 5, ...};
int acc= 0;
int i =  0;
while(i < dataSet.length){
    if (dataSet[i]%2 ==1){
        acc += dataSet[i];
    }
    i++;
}
```

As a thought experiment, how might you modify the pattern to tell if at least one element of the data set is exactly 7 (`== 7`)?  What `type` should the accumulator variable be?  What is it's initial value?  How might you modify it in the loop?
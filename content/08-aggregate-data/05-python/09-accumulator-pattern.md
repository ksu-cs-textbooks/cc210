---
title: "Accumulator Pattern"
pre: "9. "
weight: 90
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
  * generally `1`, `0`, `""`, or and empty list/array
*  Loop through every element of the `dataSet`
  * <em>Optionally</em> filter the elements
*  Update the accumulator for the element
*  AFTER the loop the accumulator variable holds the value(s) you want

To add up all the odd elements of list of integers, one might

```python
data_set = [1, 2, 3, 4, 5, ...]
acc= 0;
i =  0;
while i < len(data_set):
    if data_set[i]%2 ==1):
        acc += data_set[i]
    i += 1
```

As a thought experiment, how might you modify the pattern to tell if at least one element of the data set is exactly 7 (`== 7`)?  What should the accumulator variable's initial value be?  How might you modify it in the loop?
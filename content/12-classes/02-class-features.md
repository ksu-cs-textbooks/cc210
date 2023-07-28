---
title: "Class Features"
pre: "2. "
weight: 20
---

![Car UML](/images/12-class/car_UML.png)

## Class Attributes

Consider the above UML for a car.  It has 3 "class level" attributes, those underlined in the UML.  These are variables that belong to the class, not a particular instance, and thus are shared by all the instances.  Class features are denoted by an underline on the UML.

The Ford F-Series truck is a well selling truck model.  If we were to write a program dealing with the manufacture and sales of this truck, we would have millions of instances.  If each instance had <b>instance attributes</b> for make and model we would waste billions of bytes of memory.  By making this a class-level attribute, all instances of the class have access to a single copy of the data.

Additionally, it would make sense that at the class-level, we have a list of all vehicle identification numbers (VIN).  Keeping this information at the instance level would be horrifically inefficient.  Every time we produce a new car <b>each instance</b> of the class would have to be accessed, and a a new entry added. Not only is it a waste of time, it means we are keeping millions of copies of a list of millions numbers--oh yes, and we'll need a way to ensure each list in each instance always match.


###  Direct Access is One-way

All instances have direct access to their classes class-level attributes (and methods).  There will be language specific syntax for this.  However, class-level features do not have direct access to an instance's features.  

![One-way](/images/12-class/class_features_one_way.png)

## Class Methods

As previously discussed, class methods are denoted on the UML diagram by an underline.  Class methods will have language specific syntax for accessing other class-level features.  If access to an object is required, that object is <emp>generally</emp> included as a method parameter.



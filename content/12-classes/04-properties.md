---
title: "Properties"
pre: "4. "
weight: 40
---

![Car UML](/images/12-class/car_UML.png)

Because OOP generally results in private fields (variables), early OOP programmers were swamped with writing accessor and mutator methods.  These methods had the sole function of providing a 'public' way of getting or setting the private field.  It became so common that many programming languages developed a special "hybrid" syntax^[in some languages, properties are a special 'type', in others they are normal class fields with just a bit of syntactic sugar.  For our purposes the internal language implementation does not matter.] for this purpose called "Properties".

When a UML has public getter and setter methods  (`get_color()`, `set_color()`) AND the implementation language supports properties, properties should be used.  

Both <a href="https://www.w3schools.com/java/java_encapsulation.asp">Java</a> and <a href="https://www.geeksforgeeks.org/python-property-function/">Python</a> support properties.  Details will be in your language specific section.

When an attribute only has a 'setter' method it is often referred to as a read only property.  Read-only properties are often set by the constructor and never changed.
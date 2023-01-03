---
title: "Access Modifiers"
pre: "3. "
weight: 30
---

![Car UML](/images/12-class/car_UML.png)


You will notice that each feature of the class `Car` is labeled with a plus or minus sign.  This informs programmers how to control access to the feature.  

### `+`  Public
Public access means the code <b>outside of the class definition</b> are expected to be able to access this feature.  Generically this is referred to as "public".  Constructors are almost always public, as are many methods.

### `-` Private

Private access means that this feature should only be referenced by code <b>inside of the class definition</b>.  Some methods and nearly all attributes are typically private.

### Implementation

Implementation in code depends on the implementation language.  Some languages, like Java, strictly enforce access modifiers, making it impossible for coders to access "private" features outside a class definition.  Other languages, like Python do not enforce any restrictions, and instead depend on coders to voluntarily follow the convention.   
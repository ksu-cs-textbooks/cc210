---
title: "Driver Classes"
pre: "7. "
weight: 70
---

Instance class are not normally executable.  That is they may contain lots of fields (attributes) and methods, but generally have no `main()` method.  The technique we will use for the next few modules will be to have a companion driver class.

![Driver and Ingredient UML](/images/07-object/driver_ingr_UML.png)

In the UML class diagram above you will see we added a separate class `Driver`,  which has one method and no attributes.  

The first thing you may notice is that the method is <u>underlined</u>.  In UML, underlined class element are class-level attributes or objects.  Each language may implement these differently, but in general to access a class element all one needs is the class name, so `Driver.main()` will generally call the class-method `main()` in the class `Driver`.  Class-features can <b>only</b> be called by using the class name.

Next you may observe the dotted line arrow.  This indicates that the class `Driver` depends on the class `Ingredient`.  For our purposes this means:

* `Ingredient` must work correctly for `Driver` to work correctly
* `Driver` must include, use, import or somehow have access to `Ingredient`
  * We will cover how to do this for you specific language later in this module
* We anticipate that at least one method in `Driver` will make or access an `Ingredient` object.

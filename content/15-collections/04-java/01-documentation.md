---
title: "Documentation"
pre: "1. "
weight: 10
---

Java includes an extensive library of classes that can be included in any Java program. These classes are included as part of the Java Development Kit, or JDK, which includes the Java compiler that we use to build our programs.

Thankfully, the developers of the Java programming language have also written an extensive online manual that explains all of the features of the Java library in detail. Many developers refer to this manual as the **Java API**, or sometimes simply the **documentation** for the Java programming language. 

To explore the Java API, we can start on [this webpage](https://docs.oracle.com/javase/8/docs/api/). That link goes directly to the Java API for Java version 8, but it is very easy to find the manual for other versions of Java as well. There is a more technical version of the documentation found [here](https://docs.oracle.com/javase/8/docs/index.html) if we'd like to dive even deeper.

On the home page of the Java API, we'll see several items. To the left is a list of all the classes included in the Java library, so we can quickly explore and find the exact class we are looking for. If we'd like to browse, the panel to the right lists an overview of all of the **packages** included in the Java library. A **package** is a set of classes that are all related somehow, giving us a nice layer of organization to our code.

Here are some Java packages that we may want to explore as we continue to develop more advanced programs using Java:

* `java.io`---classes for handling input and output and working with the file system.
* `java.lang`---classes that are integral to the Java programming language, such as the core data types and exceptions
* `java.math`---classes for dealing with arbitrarily large or precise numbers
* `java.net`---classes for building networked applications
* `java.nio.file`---classes for interfacing with the file system
* `java.time`---classes for dealing with dates and times
* `java.util`---collection classes and some miscellaneous utilities

In this module, we'll mostly explore a few of the collection classes in the `java.util` package. 
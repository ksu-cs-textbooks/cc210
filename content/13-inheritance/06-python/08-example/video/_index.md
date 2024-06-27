---
title: "Python Example"
pre: "6.P. "
weight: 61
hidden: true
date: 2019-11-03T00:00:26-05:00
---

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

{{< youtube TVY2fiwwjkU >}}

Now that we've learned all about using inheritance and polymorphism in our programs, let's work through an example program together to see how we can build a much more complex program using multiple classes that use inheritance.

As always, we'll start with a problem statement. Here it is!

That looks pretty complex! Thankfully, we can break it down into a set of related classes to make the task quite a bit more bearable.

For this program, we'll be following this UML diagram to build our classes and their overall structure. Again, it looks very complex, but the vast majority of this is just simple structure and short methods to explore how inheritance works in a real program.

So, let's start with the topmost class on the inheritance hierarchy, the Tool class. It is very simple, since it only contains a default constructor and an abstract method. So, we can quickly build that class directly from the UML diagram and move on.

The next class we'll look at is the Wrench class, which inherits from tool. In that class, we have a `length` attribute, which must be set in the constructor. as well as a property getter method for length.

In addition, the Wrench class declares an abstract method called `tighten()` which will need to be overridden by child classes that inherit from Wrench. That method accepts two parameters, a clearance that tells us how much room we have for our wrench, and the size of the nut or bolt to be tightened.

That's all for the Wrench class. We can also look at the Saw class, which is very similar. The only major difference is that the Saw class declares an abstract method named `cut()`, which accepts a length of an object to be cut and the material it is made of.

There we go! That is the structure of the three parent classes in the diagram. Before we move on, let's take a minute to verify the structure of these classes before continuing.

---

{{< youtube 3diQJrArA5c >}}

Next, let's take a look at the AdjustableWrench class. We can quickly build the constructor, attributes, and property getters just based on the UML alone, which is seen here. So, we'll take a deeper look at the methods in this class, just to understand how they work.

First, the `describe()` method, which is declared all the way back in the parent Tool class, needs to be overridden with an implementation. So, we can return a string giving information about this class.

When we do, it might be tempting to use the `length` attribute right here. However, if we do, we'll quickly realize that `length` is actually a private attribute in the parent Wrench class. So, we'll need to use the public `length` property getter instead. It is a simple mistake to make that can be frustrating to fix later.

The other method we must override and implement is the `tighten()` method. To really understand how it works, we should probably look at what an adjustable wrench is. Here's a quick image! As you can see, the size of nut or bolt the wrench can adjust varies between a minimum and maximum size. So, in our `tighten()` method, we need to check and make sure the clearance is at least as large as the length of our wrench, and also that the size of nut or bolt to be tightened is between its minimum size and maximum size.

Once we have the code for the AdjustableWrench class complete, it is super easy to copy and paste that code into the CombinationWrench class and make a few changes to make it work there. Specifically, we'll need to adjust the `tighten()` method to take into account the fact that a CombinationWrench can only adjust one size of nut or bolt.

So, the `tighten()` method is quite a bit simpler in the CombinationWrench class.

We can also do the same for an OpenEndWrench, updating the `tighten()` method to check if either end of the wrench will fit the nut or bolt.

There we go! That's all it takes to build the classes we need to represent various types of wrenches. Before we move on, we should once again verify the structure of these classes is correct before continuing.

---

{{< youtube 4ccSRmeQuKk >}}

Now that we've worked on the child classes of Wrench, we can do the same for the classes that inherit from Saw. The most complex of these is CrossCutSaw. One of the more difficult parts is to realize that the list of materials is given as a string, so we'll need to use the split method to make a list of those items. Then, when we return them, we can use the join method to make a string of the items again. The textbook has a good discussion of why this is a helpful way to handle data stored in a list inside of our class.

Once we have our materials in a list, we can write a simple `findMaterial()` method to determine if a material is contained in our list. Of course, there are some library methods in Python that can do this too, but we'll just code it ourselves since it is pretty easy.

Then, we can use that method in our `cut()` method, which determines if the object described in the parameters can be cut by this saw. We'll check to make sure the object is smaller than the length of the saw, and that the object is made of a material that our saw can cut. If so, we'll return true.

Once we've built the CrossCutSaw class, we'll see that the HackSaw class is a very similar, but much simpler, version of the same idea. So, it is relatively easy to adapt that code here, adjusting the `cut()` method to only allow metal as a material.

Once again, let's stop there for a minute and make sure the structure of these classes are correct before continuing.

---

{{< youtube TC9wn_QVcO4 >}}

Finally, we are ready to build the methods in our Main class. Looking at the UML diagram, we'll create two helper methods as well as the `main()` method.

First, we should work on the method to read input from the user. So, we'll start by using try and with statements to open the input file, read the first line to get the number of tools, and instantiate an empty list to store those tools.

Then, we can create a for loop using that number of tools to determine how many times we should read input from the file.

Inside of that loop, we'll read a line of input, and split it into individual parts.

We know that the first part of each line should be the name of the tool, so we'll need a bunch of It-Then-Else statements to figure out exactly which tool we are reading. Then, inside of each one, we can get the attributes needed for the tool from the rest of the line, and create the appropriate object and append it to the list of tools. Since we know that each tool will have a length, we can put that attribute outside of the chain of If-Then-Else statements.

There we go! That will handle the input. Next, we'll need another method to handle finding the tool for the job based on input from the user. This method will accept a string as input giving the query from the user. So, once again, we'll use the `split()` method to split it into parts, and then check to see if the first part is either "tighten" or "cut".

Then, inside of those blocks, we can parse the attributes we'll need to find the right tool. For tighten, we'll need the clearance and the size. For cut, we'll need the length, as well as the material.

Then, we'll use an enhanced for loop to iterate over each of the tools in our array of tools.

Inside of that loop, we'll use the `isinstance` method to see if the tool is either a wrench or a saw.

If it is the type we need, we can call either the `tighten()` or `cut()` method to see if that tool can do the job. Those methods will return `True` if so, or `False` if not.

So, if it returns `True`, this method should return that tool as the one that can do the job.

However, there are several situations where we won't find a tool that works for the job. So, what should we return in that case?

In Python, we can use the value `None` to represent an object that doesn't exist. So, we'll return that value in cases where we can't find a tool that matches our need.

That's it for the `find_tool()` method. That just leaves the `main()` method.

In the main method, we'll start by making sure we've received a command-line argument. If not, we'll just print an error and end the program.

Then, we'll use the `read_input()` method to read input from the file given as the command-line argument. That method returns a list of tools, so we'll store that in a variable named `tools` in main.

Of course, if the file isn't read properly, we could get an empty list of tools. So, we'll need to check and make sure it isn't empty before continuing. If it is empty, we'll print an error and exit.

Once we have a list of tools, we'll need to read a query from the user. So, we'll use a try with resources statement to handle that.

Inside, we'll read a query from the user, and see if we can find a tool that meets that need.

If the tool we get is not `None`, we can print a description of the tool that will work for our task. However, if the `find_tool()` method returns `None`, we'll print an error instead.

There we go! That's all it takes to make this program work. As we've discussed before, if we do a good job building the rest of the program, our `main()` method really should look like an outline of the entire program, calling methods and sharing data between them as needed. See if you can complete this example yourself!

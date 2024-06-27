---
title: "Java String Formatting"
pre: "4.J. "
weight: 40
date: 2019-09-09T00:00:26-05:00
hidden: true
---

{{< youtube _sxpOzam2mU >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

#### Video Script

One of the most powerful uses of strings in our programs is to provide helpful output back to the user. When we create that output, many times we need to include information from a number of variables. Thankfully, there are a couple of ways we can do that.

First, we can use string concatenation, just like we learned previously in this chapter. In this example, we have a couple of variables storing data, and then a print statement. In the print statement, we are using string concatenation to add each variable's value to the output. So, as our program executes that line of code, it will first refer to the `sum` variable and get its value. Then, it will do the same for the `avg` variable. Finally, it will then be able to produce the desired output, as shown below that line.

However, there is a much more powerful way for us to output strings of data, and this method allows us to impose some more formatting on the output as well. For this example, we must created a _formatted string_ that defines the structure of our output. In this case, we have that formatted string stored in the `output` variable.

So, to execute this program, first we'll get to the `String.format()` method, which will then reference the `output` variable as the first input. That will give us the formatted string that contains the desired structure of the output. So, we'll place that in a comment at the bottom of the code, and then update it to see what the Java program stores in memory as it creates the output.

Next, it will reference the `name` variable, and replace the first placeholder, `%s`, with the value of that variable. We use the placeholder `%s` because we are replacing it with a string. So, we'll update our output string in memory with the value stored in the `name` variable.

Then, we'll look at the `sum` variable, and use it to replace the second placeholder in our format string. This placeholder, `%5d`, tells us that we would like to use an integer, or "decimal number" which is where the "d" comes from, and format it so that it is exactly 5 characters wide. By default, this will add spaces to the front of the number if needed. So, we'll see "123" in the output, but with two additional spaces in front of it.

Finally, we'll use the `avg` variable to fill in the last placeholder, `%8.4f`. This placeholder is quite complex, but it is easy to describe. First, we know that we are outputting a floating-point number due to the "f" included in the placeholder. Next, the first number, 8, gives the total width, including the decimal place. Following that, we have a 4, giving the number of places after the decimal place. So, the number 1.23 will be converted to 1.2300, with two additional spaces added to the front to make the entire value 8 characters in length.

Once we've done those replacements, we can now see the final output of our program shown at the bottom of the code.

As we saw earlier with string parsing, there are a variety of ways we can use strings to create useful output for our users. We can use whichever method we are most comfortable with or the one that best fits our needs.

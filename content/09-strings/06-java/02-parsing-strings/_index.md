---
title: "Parsing Strings"
pre: "2. "
weight: 20
---

<!-- {{% youtube kBbqnMUddKs %}}-->

<!-- [Video Materials]({{<relref "./video">}}) -->

<!-- TODO Update Video -->

In many programs, we'll be reading input from the user into a string variable, and then parsing that input into the various data types we need. Parsing is a two-step process: tokenization and conversion.

Let's explore parsing by starting with a program that reads a line from the keyboard.

```java
// Load required classes

public class Example{
  
  public static void main(String[] args) throws Exception{
    
    // Scanner variable
    Scanner reader = new Scanner(System.in);
    
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    
  }
  
}
```

This code creates a variable named `reader`, which is a Scanner object in Java. we recommend you always read in Strings using the `.nextLine()` method.   Once we've read in a line, we split it into tokens (parts).

## Tokenization

Tokenization refers to splitting a large input into smaller parts, its tokens.  Each token is delimited by special characters, called delimiters.  In normal text, words (the tokens) are delimited by so called "white space"^[which derives from the blank spaces on standard paper].  In a computer String variable these spaces are not blank, but rather contain "unprintable" characters as shown in the following table
<table>
    <tr><th>ASCII</th><th>char</th><th> thing</th></tr>
    <tr><td>32</td><td>' '</td><td>space</td></tr>
    <tr><td>9</td><td>'\t'</td><td>tab</td></tr>
    <tr><td>13</td><td>'\r'</td><td>carriage return</td></tr>
    <tr><td>10</td><td>'\n'</td><td>new line</td></tr>
</table>

In general the problem statement or program specification will provide some clue as to appropriate delimiters.

### Split

For example, let's say we'd like to tokenize the following input from the user:

```tex
This 1 2.0 true
The second line
```

We'll assume that we've already created our `reader` variable using the skeleton code given above. So, to parse this input, we could use the following code

```java
String line1 = reader.nextLine();  
   // line1 == "This 1 2.0 true"
String[] line1Parts = line1.split(" ");
  // line1Parts == {"This", "1", "2.0", "true"}
String line2 = reader.nextLine();  
   // line2 == 
String[] line2Parts = line1.split(" ");
  // line2Parts ==   
```

Let's go through this code and see how it works. First, we read a single line of input from the user using the `reader.nextLine()` method. Then, we split that line into individual parts using the `split` method of the string variable `line1`. Inside of the split method, we need to give the string that we'd like to use as our _delimiter_. So, in this case, we'll just provide a string that contains a single space to use the space character as our delimiter. 

That will create an array of strings named `line1Parts`, which will contain four elements. In this case, the first element will be "This", the second element will be "1" and so on. 

We then do the same process again for the second line.  What will the values of `line2` and `line2Parts` be?

{{% notice note "String.split() and Regular Expressions" %}}

Technically, Java's `String.split()` method we are using actually uses a _regular expression_ to perform the split operation. A regular expression is a specially formatted string that is used to define a search pattern in a string. For example, we could write a regular expression to match words that begin with a number, contain at least three letters, and then end with the letter "a". That regular expression would be "\b\d.{3,}a\b", by the way.

So, as input, we are not just providing a delimiter as a string, but we are actually creating a _regular expression_ that the computer users to determine where to split the string. Thankfully, if we provide a single character in a string as input, it will simply look for that character in the string, and split the string anywhere that it finds the character we provide.

So, we can just pretend we are providing a single delimiter string to this operation for now, but behind the scenes it is capable of doing so much more. 

You can learn more about regular expressions in Java here:

[Java Regular Expressions](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)

{{% /notice %}}


## Conversion (finally)

First, we determine if a token can be converted into a literal value of a certain type^[Often you will know the intended type of the input].  Consider the token "2.".  
*  Can you parse this into a double?  Yes, `double temp = 2.0;` will compile just fine.  
*  How about an int? No, `int temp = 2.0;` does not compile.

What about the token "2", can it be converted to : double, int?

Once we determine the token <b>can</b> be converted, we do the conversion.

For example, let's say the user has provided the following text as input:

```tex
1 This 2.0 is true
```

We could parse that input into individual variables using this block of code:

```java
String line = reader.nextLine();
String[] tokens = line.split(" ");  
int i1 = Integer.parseInt(tokens[0]);        // 1
String s1 = tokens[1];                       // This
double d = Double.parseDouble(tokens[2]);    // 2.0
String s2 = tokens[3];                       // is
boolean b = Boolean.parseBoolean(tokens[4]); // true
```


## Reading More Input

When using a while-loop to read from the terminal, we must use a sentinel value to "signal" the end of input.  Typically, an empty line^[just hit the return/enter key] is used. `Scanner.nextLine()` returns the empty string in this case. Then, we can use an **If-Then** statement to determine if the user is finished providing input.

Here's a great way to handle this situation in Java:

```java
String line = " "; // a space
while(line.length() >0){
  line = reader.nextLine();
  
  if(line.length() > 0){
      // parse the input
  }

}
```

In this case, the program will continue to read input from the user until the user enters a blank line of input by just pressing the Enter key on the keyboard.

## Practice

Let's take a minute to get some practice parsing strings of input for our programs.

Complete 'StringParsing.java' to meet the following problem statement:

> Write a program that can find the sum of an undetermined number of inputs provided on two lines. The first line of input will contain one or more integers, separated by spaces. The second line of input will contain one or more floating point numbers, separated by commas. The program should output the sum of all inputs provided. 

So, for example, if our program receives the following input:

```tex
1 2 3 4 5
1.25,2.5,3.75
```

we should print out "22.5" as the result. 

Assuming we already have our skeleton code, we can quickly work through this problem statement. First, we'll need to read a line of input and split it using the space character as our delimiter:

```java
String input = reader.nextLine();
String[] splits = input.split(" ");
```

That's simple enough. Now, since we don't know how many inputs might have been provided, we'll have to use a **FOREACH**^[the Java nomenclature is enhanced-For loop] loop to iterate over the inputs:

```java
String input = reader.nextLine();
String[] splits = input.split(" ");

for(String s : splits){
  
}
```

Then, inside of the **FOREACH** loop, we can just convert each input as an integer and then add it to a sum variable. We'll have to create the sum variable outside of the **FOREACH** loop, because we'll want it available <b>outside</b> of the loop.  We'll make that variable a floating point data type, since we'll be adding floating point numbers to it from the second line of input.

```java
String input = reader.nextLine();
String[] splits = input.split(" ");

double sum = 0.0;
for(String s : splits){
  sum += Integer.parseInt(s);
}
```

Next, we can read the next line of input from the user, and then split it using a comma as a delimiter. 

```java
String input = reader.nextLine();
String[] splits = input.split(" ");

double sum = 0.0;
for(String s : splits){
  sum += Integer.parseInt(s);
}

input = reader.nextLine();
splits = input.split(",");
```

Notice that we are able to reuse the variables `input` and `splits` here. This is handy, so we only have to manage one set of variables as we parse multiple lines of input.

Finally, we can use another **FOREACH** loop to iterate across the second set of inputs, parse them into a floating point value, and then add them to the sum variable. Finally, at the end, we'll print out the value of the `sum` variable.

```java
String input = reader.nextLine();
String[] splits = input.split(" ");

double sum = 0.0;
for(String s : splits){
  sum += Integer.parseInt(s);
}

input = reader.nextLine();
splits = input.split(",");

for(String s : splits){
  sum += Double.parseDouble(s);
}

System.out.println(sum);
```
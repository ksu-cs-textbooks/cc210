---
title: "Throw and Throws"
pre: "4. "
weight: 40
---

{{% youtube xJSxraNRqhk %}}

[Video Materials]({{<relref "./video">}})

Beyond catching exceptions, there are a few other important concepts to learn related to exceptions. Let's go over a couple of them.

## Throws

 When the Java compiler finds a checked exception, we must either surround that code in a **Try-Catch** statement, or we must declare the exception to be thrown by adding `throws` to our method declaration, followed by the exception type. 

Here's an example:

```java
import java.util.Scanner;
import java.io.File;

public class Throw{
  
  public static void main(String[] args){
    
    Scanner reader;
    
    reader = new Scanner(new File("input.txt"));
    int x = Integer.parseInt(reader.nextLine());
    System.out.println(x);
    
  }
}
```

The code above handles user inputs. However, it does not includes the `throws` keyword. So, when we try to compile this code, we'll get the following error message.

```tex
8j-except/Throw.java:11: error: unreported exception FileNotFoundException; must be caught or declared to be thrown
      reader = new Scanner(new File(args[0]));
               ^
1 error
```

To allow this code to compile, we must simply add `throws FileNotFoundException` to the end of our method declaration to tell the compiler that we aren't going to handle that exception in our code. We'll also have to add `import java.io.FileNotFoundException` to the top of the file. Notice that we aren't using `throws Exception` this time, since we now know more about how exceptions work. As we'll discuss later in this chapter, it is always better to include a specific exception instead of a generic one whenever possible. 

Of course, we may also want to use a **Try-Catch** statement to handle this error directly in our code. We'll discuss those tradeoffs later as well.

## Throw

We can also generate our own exceptions using the `throw` keyword. This allows us to create new exceptions whenever needed. Let's look at an example:

```java
import java.util.Scanner;
import java.io.File;
import java.lang.ArithmeticException;
import java.io.FileNotFoundException;

public class Throw{
  
  public static void main(String[] args) throws FileNotFoundException{
    
    Scanner reader;
    
    reader = new Scanner(new File("input.txt"));
    
    double x = Double.parseDouble(reader.nextLine());
    double y = Double.parseDouble(reader.nextLine());
    
    if(y == 0.0){
      throw new ArithmeticException("Divide by Zero!");
    }else{
      System.out.println(x / y);
    }
    
  }
}
```

In this code, we are asking the user to input two floating point numbers. Then, we will output the first number divided by the second. However, we want to avoid the situation where the second number, the divisor, is $0$. Since Java doesn't generate an ArithmeticException when dividing by $0$ using floating point numbers, we can do that ourselves using an **If-Then** statement and the `throw` keyword. 

Following the `throw` keyword, we must create a new Exception. In this case, we are creating a new ArithmeticException, but any of the exception types we've learned about so far will work the same way. Inside of the parentheses, we can provide a helpful error message to go along with this exception. 

## Try It!

Let's see if we can use these keywords in another example. We'll start with this code:

```java
import java.util.Scanner;
import java.io.File;

public class Throw{
  
  public static void main(String[] args){
    
    Scanner reader;
    
    reader = new Scanner(new File(args[0]));
   
    // *** ADD CODE HERE ***
    
  }
}
```

Place this code in `Throw.java` and modify it to do the following:
1. If the file given in `args[0]` does not exist, it should throw a `FileNotFoundException`. We'll need to add the `throws` keyword and additional information in the correct place.
2. It should read a single string of input from the user. To make this simple, don't forget to use the `trim()` method to remove any extra whitespace!
3. If the string does not begin with a capital letter, it should throw a new [IllegalArgumentException](https://docs.oracle.com/javase/8/docs/api/java/lang/IllegalArgumentException.html) that contains the error message "Proper Capitalization Required!"
4. Of course, if the string is empty, it should throw a `StringIndexOutOfBoundsException` when it tries to access the first character of the string. (_Hint: Will the `String.charAt()` method throw this exception for us? We can check the Java Documentation to find out_)
5. Otherwise, it should print the string to the terminal. 

{{% notice note "Command-Line Arguments" %}}

In the example above, we are using the code `args[0]` to access the first command-line argument provided to the program. As you can tell by the data type in the parameter of the `main` method, `args` is an array of strings.

When running a Java program from the terminal, we can provide command-line arguments after the name of the file, as in this example:

```bash
java Throw input.txt
```

In this example, the string `"input.txt"` will be stored in `args[0]` as the first command-line argument, and it will be accessible in the program. This is a great way to run a program by providing an input file to read from.

More command-line arguments can be included, separated by spaces:

```bash
java Throw input.txt output.txt 
```

In this example, `"input.txt"` would be stored in `args[0]` and `"output.txt"` would be stored in `args[1]`. 

{{% /notice %}}

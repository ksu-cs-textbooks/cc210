---
type: "reveal"
hidden: true
---
<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program to accept a list of numbers, one per line. Input is provided from a file if one is provided as the first command line argument. If a file is not provided, input should be read from the terminal.</p>
	<p style="font-size: 0.5em">The numbers can either be whole numbers or floating point numbers. The program should continue to accept input until a number equal to 0 is input. Of course, if the input in a file ends before a 0, that can be treated as the end of the input.</p>
	<p style="font-size: 0.5em">Once 0  is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input). Sample outputs are shown below.</p>
	<p style="font-size: 0.5em">The program should catch and handle all common exceptions. When an exception is caught, the program should print the name of the exception, followed by the message included in the exception. It should then continue to accept input (if possible). Specifically, if it is unable to open the file provided, input should be read from the terminal.</p>
</section>
<section>
  <h2>Zoinks!</h2>
	<img class="stretch plain" src="/cc210/images/zoinks.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/5hdg7p9NE7VlLWaeRK">Boomerang via Giphy</a></p>
	<p>Let's break it down into smaller parts</p>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">public class Example{
<br>
  public static void main(String[] args){
<br>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>import java.util.Scanner;
import java.io.File;</mark>
<br>
public class Example{
<br>
  public static void main(String[] args){
    <mark>Scanner scanner;</mark>
    <mark>scanner = new Scanner(new File(args[0]));</mark>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    scanner = new Scanner(<mark>new File(args[0])</mark>);
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
<br>
public class Example{
<br>
  public static void main(String[] args)<mark> throws... </mark>{
    Scanner scanner;
    scanner = new Scanner(<mark>new File(args[0])</mark>);
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
<br>
public class Example{
<br>
  public static void main(String[] args)<mark><s> throws... </s></mark>{
    Scanner scanner;
    scanner = new Scanner(<mark>new File(args[0])</mark>);
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
<mark>import Java.io.FileNotFoundException;</mark>
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    <mark>try{</mark>
      scanner = new Scanner(new File(args[0]));
    <mark>}catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " ...);
    }</mark>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import Java.io.FileNotFoundException;
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " ...);
      <mark>scanner = new Scanner(System.in);</mark>
    }
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import Java.io.FileNotFoundException;
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(<mark>args[0]</mark>));
    }catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " ...);
      scanner = new Scanner(System.in);
    }
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import Java.io.FileNotFoundException;
<mark>import Java.lang.ArrayIndexOutOfBoundsException;</mark>
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " ...);
      scanner = new Scanner(System.in);
    }<mark>catch(ArrayIndexOutOfBoundsException e){
      System.out.println("ArrayIndexOutOfBounds...");
      scanner = new Scanner(System.in);
    }</mark>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import Java.io.FileNotFoundException;
import Java.lang.ArrayIndexOutOfBoundsException;
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " ...);
      scanner = new Scanner(System.in);
    }catch(ArrayIndexOutOfBoundsException e){
      System.out.println("ArrayIndexOutOfBounds...");
      scanner = new Scanner(System.in);
    }
<br>
    <mark>try(
      Scanner reader = scanner
    ){</mark>
<br>
        // more code here
<br>
    <mark>}catch(Exception e){
      System.out.println("Exception: " + e);
    }</mark>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import Java.io.FileNotFoundException;
import Java.lang.ArrayIndexOutOfBoundsException;
<br>
public class Example{
<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("FileNotFoundException: " ...);
      scanner = new Scanner(System.in);
    }catch(ArrayIndexOutOfBoundsException e){
      System.out.println("ArrayIndexOutOfBounds...");
      scanner = new Scanner(System.in);
    }
<br>
    try(
      Scanner reader = scanner
    ){
<br>
        <mark>// more code here</mark>
<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Input is provided from a file [or] read from the terminal.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  double input = reader.nextDouble();
  if(input == 0.0){
    break;
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  <mark>double input = reader.nextDouble();</mark>
  if(input == 0.0){
    break;
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... <mark>whole numbers or floating point numbers</mark>... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  double input = reader.nextDouble();
  <mark>if(input == 0.0){
    break;
  }</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... <mark>accept input until a number equal to 0 is input.</mark></p>
    <p style="font-size: .7em">The program should catch and handle all common exceptions.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  double input = <mark>reader.nextDouble()</mark>;
  if(input == 0.0){
    break;
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  <mark>try{</mark>
    double input = reader.nextDouble();
    if(input == 0.0){
      break;
    }
  <mark>}</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  try{
    double input = <mark>reader.nextDouble()</mark>;
    if(input == 0.0){
      break;
    }
  }<mark>catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  try{
    double input = <mark>reader.nextDouble()</mark>;
    if(input == 0.0){
      break;
    }
  }catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }<mark>catch(NoSuchElementException e){
    System.out.println("NoSuchElementException");
    break; // out of input, so we should stop there
  }</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">list of numbers, one per line... whole numbers or floating point numbers... accept input until a number equal to 0 is input.</p>
    <p style="font-size: .7em"><mark>The program should catch and handle all common exceptions.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(true){
  try{
    double input = reader.nextDouble();
    if(input == 0.0){
      break;
    }
  }catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }catch(NoSuchElementException e){
    System.out.println("NoSuchElementException");
    break; // out of input, so we should stop there
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>double minimum = 0.0;
double maximum = 0.0;</mark>
<br>
while(true){
  try{
    double input = reader.nextDouble();
    if(input == 0.0){
      break;
    }
  }catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }catch(NoSuchElementException e){
    System.out.println("NoSuchElementException");
    break; // out of input, so we should stop there
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>double minimum = 0.0;
double maximum = 0.0;</mark>
<br>
while(true){
  try{
    double input = reader.nextDouble();
    if(input == 0.0){
      break;
    }
    <mark>if(input &lt; minimum || minimum == 0.0){
      minimum = input;
    }
    if(input > maximum || maximum == 0.0){
      maximum = input;
    }</mark>
  }catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }catch(NoSuchElementException e){
    System.out.println("NoSuchElementException");
    break; // out of input, so we should stop there
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>double minimum = 0.0;
double maximum = 0.0;</mark>
<br>
while(true){
  try{
    double input = reader.nextDouble();
    if(input == 0.0){
      break;
    }
    <mark>if(input &lt; minimum || minimum == 0.0){
      minimum = input;
    }
    if(input > maximum || maximum == 0.0){
      maximum = input;
    }</mark>
  }catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }catch(NoSuchElementException e){
    System.out.println("NoSuchElementException");
    break; // out of input, so we should stop there
  }
}
<br>
<mark>System.out.println("Maximum: " + maximum);
System.out.println("Minimum: " + minimum);</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">double minimum = 0.0;
double maximum = 0.0;
<br>
while(true){
  try{
    double input = reader.nextDouble();
    if(input == 0.0){
      break;
    }
    if(input &lt; minimum || minimum == 0.0){
      minimum = input;
    }
    if(input > maximum || maximum == 0.0){
      maximum = input;
    }
  }catch(InputMismatchException e){
    System.out.println("InputMismatchException");
    reader.next(); // ignore bad input
  }catch(NoSuchElementException e){
    System.out.println("NoSuchElementException");
    break; // out of input, so we should stop there
  }
}
<br>
System.out.println("Maximum: " + maximum);
System.out.println("Minimum: " + minimum);
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Once 0 is received or the input ends, the program should print the largest and smallest number provided as input (not including the 0 to end input).</p>
  </div>
</section>
<br>
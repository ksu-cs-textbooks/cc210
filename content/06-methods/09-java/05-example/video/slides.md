---
type: "reveal"
hidden: true
---
<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program that calculates the minimum, maximum, sum, and average of a list of numbers. The numbers should be read from a file provided as a command-line argument. The file should contain a single number on each line.</p>
	<p style="font-size: 0.5em">The program should handle all reasonable exceptions. If the input file is not provided or cannot be read, it should print "Error opening file." If the input file contains a value that cannot be converted to a number, it should print "Error parsing input." Any other errors should cause the program to print "Unknown error."</p>
	<p style="font-size: 0.5em">When printing, all decimal values should be rounded to the nearest tenth (one decimal place). The final output of the program should look similar to the following:</p>
	<pre style="font-size: 0.5em">Minimum: 24.0
Maximum: 183.0
Sum: 1236.4
Average: 102.3</pre>
</section>
<section>
  <h2>Uhhhhh...</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/3og0INyCmHlNylks9O/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/reactionseditor-classic-facepalm-3og0INyCmHlNylks9O">Giphy</a></p>
	<p>Let's break it down into smaller parts</p>
</section>
<br>
<br>
<br>
<section>
  <h2>Use Functions!</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/Cv2CCge3AtbCE/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://giphy.com/gifs/star-trek-Cv2CCge3AtbCE">Giphy</a></p>
	<p>Let's break it down into <b style="color:#512888">functions</b></p>
</section>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .32em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;
import java.lang.NumberFormatException;
<br>
public class Example{
<br>
  static double[] readInput(String filename){
    try(
      Scanner scanner = new Scanner(Paths.get(filename))
    ){
<br>
      // Read input file here
<br>
    }catch(InvalidPathException e){
      System.out.println("Error opening file.");
      return new double[0];
    }catch(NoSuchFileException e){
      System.out.println("Error opening file.");
      return new double[0];
    }catch(NumberFormatException e){
      System.out.println("Error parsing input.");
      return new double[0];
    }catch(IOException e){
      System.out.println("Unknown error.");
      return new double[0];
    }
  }
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .32em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;
import java.lang.NumberFormatException;
<br>
public class Example{
<br>
  static double[] readInput(String filename){
    try(
      Scanner scanner = new Scanner(Paths.get(filename))
    ){
<br>
      // Read input file here
<br>
    }catch(InvalidPathException e){
      System.out.println("Error opening file.");
      <mark>return new double[0];</mark>
    }catch(NoSuchFileException e){
      System.out.println("Error opening file.");
      <mark>return new double[0];</mark>
    }catch(NumberFormatException e){
      System.out.println("Error parsing input.");
      <mark>return new double[0];</mark>
    }catch(IOException e){
      System.out.println("Unknown error.");
      <mark>return new double[0];</mark>
    }
  }
}</code></pre>
</section>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .32em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;
import java.lang.NumberFormatException;
<br>
public class Example{
<br>
  static double[] readInput(String filename){
    try(
      <mark>Scanner scanner = new Scanner(Paths.get(filename));</mark>
      <mark>Scanner scanner2 = new Scanner(Paths.get(filename))</mark>
    ){
<br>
      // Read input file here
<br>
    }catch(InvalidPathException e){
      System.out.println("Error opening file.");
      return new double[0];
    }catch(NoSuchFileException e){
      System.out.println("Error opening file.");
      return new double[0];
    }catch(NumberFormatException e){
      System.out.println("Error parsing input.");
      return new double[0];
    }catch(IOException e){
      System.out.println("Unknown error.");
      return new double[0];
    }
  }
}</code></pre>
</section>
<br>
<br>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .32em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;
import java.lang.NumberFormatException;
<br>
public class Example{
<br>
  static double[] readInput(String filename){
    try(
      Scanner scanner = new Scanner(Paths.get(filename));
      Scanner scanner2 = new Scanner(Paths.get(filename))
    ){
<br>
      <mark>// Read input file here</mark>
<br>
    }catch(InvalidPathException e){
      System.out.println("Error opening file.");
      return new double[0];
    }catch(NoSuchFileException e){
      System.out.println("Error opening file.");
      return new double[0];
    }catch(NumberFormatException e){
      System.out.println("Error parsing input.");
      return new double[0];
    }catch(IOException e){
      System.out.println("Unknown error.");
      return new double[0];
    }
  }
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .5em"><code class="java">// read the input
double[] numbers = new double[???];</code></pre>
</section>
<br>
<br>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .5em"><code class="java">// read the number of lines
int lines = 0;
while(scanner.hasNext()){
  scanner.nextLine(); // read the next line, but don't store it
  lines++;
}
<br>
// read the input
double[] numbers = new double[lines];</code></pre>
</section>
<br>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .5em"><code class="java">// read the number of lines
int lines = 0;
while(scanner.hasNext()){
  scanner.nextLine(); // read the next line, but don't store it
  lines++;
}
<br>
// read the input
double[] numbers = new double[lines];
<br>
int index = 0;
while(scanner2.hasNext()){
  String line = scanner2.nextLine();
  numbers[index] = Double.parseDouble(line);
  index++;
}
</code></pre>
</section>
<br>
<section>
 <h4>Read Input File</h4>
    <pre class="stretch" style="font-size: .5em"><code class="java">// read the number of lines
int lines = 0;
while(scanner.hasNext()){
  scanner.nextLine(); // read the next line, but don't store it
  lines++;
}
<br>
// read the input
double[] numbers = new double[lines];
<br>
int index = 0;
while(scanner2.hasNext()){
  String line = scanner2.nextLine();
  numbers[index] = Double.parseDouble(line);
  index++;
}
<br>
// return the input
return numbers;
</code></pre>
</section>
<br>
<br>
<section>
 <h4>Max & Min</h4>
    <pre class="stretch" style="font-size: .4em"><code class="java">static double min(double[] numbers){
  double minimum = 0;
  if(numbers.length > 0){
    minimum = numbers[0];
  }
  for(double d : numbers){
    if(d < minimum){
      minimum = d;
    }
  }
  return minimum;
}
<br>
static double max(double[] numbers){
  double maximum = 0;
  if(numbers.length > 0){
    maximum = numbers[0];
  }
  for(double d : numbers){
    if(d > maximum){
      maximum = d;
    }
  }
  return maximum;
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Sum & Average</h4>
    <pre class="stretch" style="font-size: .6em"><code class="java">static double sum(double[] numbers){
  double sum = 0;
  for(double d : numbers){
    sum += d;
  }
  return sum;
}
<br>
static double avg(double[] numbers){
  double sum = 0;
  for(double d : numbers){
    sum += d;
  }
  return sum / numbers.length;
}</code></pre>
</section>
<br>
<section>
 <h4>Sum & Average</h4>
    <pre class="stretch" style="font-size: .6em"><code class="java">static double sum(double[] numbers){
  <mark>double sum = 0;
  for(double d : numbers){
    sum += d;
  }
  return sum</mark>;
}
<br>
static double avg(double[] numbers){
  <mark>double sum = 0;
  for(double d : numbers){
    sum += d;
  }
  return sum</mark> / numbers.length;
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Sum & Average</h4>
    <pre class="stretch" style="font-size: .6em"><code class="java">static double sum(double[] numbers){
  double sum = 0;
  for(double d : numbers){
    sum += d;
  }
  return sum;
}
<br>
static double avg(double[] numbers){
  <mark>double sum = sum(numbers);</mark>
  return sum / numbers.length;
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Output</h4>
    <pre class="stretch" style="font-size: .43em"><code class="java">static void printOutput(double minimum, double maximum, double sum, double avg){
  System.out.println(String.format("Minimum: %.1f", minimum));
  System.out.println(String.format("Maximum: %.1f", maximum));
  System.out.println(String.format("Sum: %.1f", sum));
  System.out.println(String.format("Average: %.1f", avg));
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
<br>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    <mark>if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }</mark>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }
    <mark>double[] numbers = readInput(args[0]);</mark>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }
    double[] numbers = readInput(args[0]);
    <mark>if(numbers.length == 0){
      return;
    }</mark>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }
    double[] numbers = readInput(args[0]);
    if(numbers.length == 0){
      return;
    }
    <mark>double minimum = min(numbers);
    double maximum = max(numbers);
    double sum = sum(numbers);
    double average = avg(numbers);</mark>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }
    double[] numbers = readInput(args[0]);
    if(numbers.length == 0){
      return;
    }
    double minimum = min(numbers);
    double maximum = max(numbers);
    double sum = sum(numbers);
    double average = avg(numbers);
    <mark>printOutput(minimum, maximum, sum, average);</mark>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }
    double[] numbers = readInput(args[0]);
    if(numbers.length == 0){
      return;
    }
    double minimum = min(numbers);
    double maximum = max(numbers);
    double sum = sum(numbers);
    double average = avg(numbers);
    printOutput(minimum, maximum, sum, average);
    <mark>return;</mark>
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
<br>
<br>
<section>
 <h4>Main</h4>
    <pre class="stretch" style="font-size: .35em"><code class="java">import ...
<br>
public class Example{
<br>
  public static void main(String[] args){
    if(args.length != 1){
      System.out.println("Error opening file.");
      return;
    }
    double[] numbers = readInput(args[0]);
    if(numbers.length == 0){
      return;
    }
    double minimum = min(numbers);
    double maximum = max(numbers);
    double sum = sum(numbers);
    double average = avg(numbers);
    printOutput(minimum, maximum, sum, average);
    return;
  }
<br>
  static double[] readInput(String filename){...}
  static double min(double[] numbers){...}
  static double max(double[] numbers){...}
  static double sum(double[] numbers){...}
  static double avg(double[] numbers){...}
  static void printOutput(double minimum, double maximum, double sum, double avg){...}
<br>
}</code></pre>
</section>
<br>
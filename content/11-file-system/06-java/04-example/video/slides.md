---
type: "reveal"
hidden: true
---<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program that accepts three files as command line arguments. The first two represent input files, and the third one represents the desired output file. If there aren't three arguments provided, either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program. The output file may be an existing file, since it will be overwritten. </p>
	<p style="font-size: 0.5em">The program should open each input file and read the contents. Each input file will consist of a list of whole numbers, one per line. If there are any errors parsing the contents of either file, the program should print "Invalid Input" and exit. As the input is read, the program should keep track of both the count and sum of all even inputs and odd inputs.</p>
	<p style="font-size: 0.5em">Once all input is read, the program should create the output file and print the following four items, in this order, one per line: number of even inputs, sum of even inputs, number of odd inputs, sum of odd inputs.</p>
	<p style="font-size: 0.5em">Finally, when the program is done, it should simply print "Complete" and exit. Don't forget to close any open files!</p>
</section>
<section>
  <h2>Whaaaa?</h2>
	<img class="stretch plain" src="https://media.giphy.com/media/l3q2K5jinAlChoCLS/source.gif">
  <p class="imagecredit">Image Credit: <a href="https://media.giphy.com/media/l3q2K5jinAlChoCLS/source.gif">Mashable via Giphy</a></p>
	<p>Let's break it down into smaller parts</p>
</section><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Example{
  public static void main(String[] args){<br>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Write a program that accepts three files as command line arguments.</p>
    <p style="font-size: .7em">If there aren't three arguments provided, ... print "Invalid Arguments" and exit the program.</p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Example{
  public static void main(String[] args){
    <mark>if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .7em">Write a program that accepts three files as command line arguments.</p>
    <p style="font-size: .7em">If there aren't three arguments provided, ... print "Invalid Arguments" and exit the program.</p>
  </div>
</section><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java"><mark>import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;</mark><br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    <mark>try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){</mark>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
<mark>import java.nio.file.InvalidPathException;</mark><br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new Scanner(<mark>Paths.get(args[0])</mark>);
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }<mark>catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
<mark>import java.nio.file.NoSuchFileException;</mark><br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new <mark>Scanner(Paths.get(args[0]))</mark>;
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }<mark>catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is <mark>not an existing file</mark>, or the output file is an existing directory, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
<mark>import java.io.IOException;</mark><br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = <mark>Files.newBufferedWriter(
                                      Paths.get(args[2]))</mark>
    ){
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }<mark>catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is not an existing file, or the <mark>output file is an existing directory</mark>, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;<br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;<br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){
      <mark>/* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */</mark>
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The first two represent input files, and the third one represents the desired output file.</p>
    <p style="font-size: .65em">...either input file is not an existing file, or the output file is an existing directory, print "Invalid Arguments" and exit the program</p>
  </div>
</section><br><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The program should open each input file and read the contents. Each input file will consist of a list of whole numbers, one per line. If there are any errors parsing the contents of either file, the program should print "Invalid Input" and exit.</p>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();<br>
}<br>
while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();<br>
}
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The program should <mark>open each input file and read the contents</mark>. Each input file will consist of a list of whole numbers, one per line. If there are any errors parsing the contents of either file, the program should print "Invalid Input" and exit.</p>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  <mark>int input = Integer.parseInt(line);</mark><br>
}<br>
while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  <mark>int input = Integer.parseInt(line);</mark><br>
}
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The program should open each input file and read the contents. Each input file will consist of a list of <mark>whole numbers</mark>, one per line. If there are any errors parsing the contents of either file, the program should print "Invalid Input" and exit.</p>
  </div>
</section><br><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  <mark>int input = Integer.parseInt(line);</mark><br>
}<br>
while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  <mark>int input = Integer.parseInt(line);</mark><br>
}
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The program should open each input file and read the contents. Each input file will consist of a list of whole numbers, one per line. If there are any <mark>errors parsing the contents</mark> of either file, the program should <mark>print "Invalid Input" and exit.</mark></p>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;<br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The program should open each input file and read the contents. Each input file will consist of a list of whole numbers, one per line. If there are any <mark>errors parsing the contents</mark> of either file, the program should <mark>print "Invalid Input" and exit.</mark></p>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;
<mark>import java.lang.NumberFormatException;</mark><br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    ){
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }<mark>catch(NumberFormatException e){
      System.out.println("Invalid Input");
      return;
    }</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">The program should open each input file and read the contents. Each input file will consist of a list of whole numbers, one per line. If there are any <mark>errors parsing the contents</mark> of either file, the program should <mark>print "Invalid Input" and exit.</mark></p>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  int input = Integer.parseInt(line);
  <mark>if(input % 2 == 0){
    //even
  }else{
    //odd
  }</mark>
}<br>
while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  int input = Integer.parseInt(line);
  <mark>if(input % 2 == 0){
    //even
  }else{
    //odd
  }</mark>
}
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">As the input is read, the program should keep track of both the count and sum of all <mark>even inputs and odd inputs.</mark></p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java"><mark>int countEven = 0;
int countOdd = 0;
int sumEven = 0;
int sumOdd = 0;</mark><br>
while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    <mark>countEven += 1;
    sumEven += input;</mark>
  }else{
    <mark>countOdd += 1;
    sumOdd += input;</mark>
  }
}<br>
while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    <mark>countEven += 1;
    sumEven += input;</mark>
  }else{
    <mark>countOdd += 1;
    sumOdd += input;</mark>
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">As the input is read, the program should <mark>keep track of both the count and sum</mark> of all even inputs and odd inputs.</p>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .35em"><code class="java">int countEven = 0;
int countOdd = 0;
int sumEven = 0;
int sumOdd = 0;<br>
while(scanner1.hasNext()){
  String line = scanner1.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    countEven += 1;
    sumEven += input;
  }else{
    countOdd += 1;
    sumOdd += input;
  }
}<br>
while(scanner2.hasNext()){
  String line = scanner2.nextLine().trim();
  int input = Integer.parseInt(line);
  if(input % 2 == 0){
    countEven += 1;
    sumEven += input;
  }else{
    countOdd += 1;
    sumOdd += input;
  }
}<br>
<mark>/* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */</mark>
    </code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">Once all input is read, the program should create the output file and print the following four items, in this order, one per line: number of even inputs, sum of even inputs, number of odd inputs, sum of odd inputs.</p>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .45em"><code class="java">writer.write("" + countEven);
writer.newLine();
writer.write("" + sumEven);
writer.newLine();
writer.write("" + countOdd);
writer.newLine();
writer.write("" + sumOdd);
writer.newLine();</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">Once all input is read, the program should create the output file and <mark>print the following four items, in this order, one per line: number of even inputs, sum of even inputs, number of odd inputs, sum of odd inputs.</mark></p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .45em"><code class="java">writer.write("" + countEven);
writer.newLine();
writer.write("" + sumEven);
writer.newLine();
writer.write("" + countOdd);
writer.newLine();
writer.write("" + sumOdd);
writer.newLine();</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">Finally, when the program is done, it should simply print "Complete" and exit. Don't forget to close any open files!</p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .45em"><code class="java">writer.write("" + countEven);
writer.newLine();
writer.write("" + sumEven);
writer.newLine();
writer.write("" + countOdd);
writer.newLine();
writer.write("" + sumOdd);
writer.newLine();<br>
<mark>System.out.println("Complete");</mark></code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">Finally, when the program is done, <mark>it should simply print "Complete" and exit</mark>. Don't forget to close any open files!</p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .45em"><code class="java">writer.write("" + countEven);
writer.newLine();
writer.write("" + sumEven);
writer.newLine();
writer.write("" + countOdd);
writer.newLine();
writer.write("" + sumOdd);
writer.newLine();<br>
System.out.println("Complete");</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">Finally, when the program is done, it should simply print "Complete" and exit. <mark>Don't forget to close any open files!</mark></p>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .31em"><code class="java">import java.util.Scanner;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.io.BufferedWriter;
import java.nio.file.InvalidPathException;
import java.nio.file.NoSuchFileException;
import java.io.IOException;
import java.lang.NumberFormatException;<br>
public class Example{
  public static void main(String[] args){
    if(args.length != 3){
      System.out.println("Invalid Arguments");
      return;
    }
    <mark>try(
      Scanner scanner1 = new Scanner(Paths.get(args[0]));
      Scanner scanner2 = new Scanner(Paths.get(args[1]));
      BufferedWriter writer = Files.newBufferedWriter(
                                      Paths.get(args[2]))
    )</mark>{
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
    }catch(InvalidPathException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NoSuchFileException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(IOException e){
      System.out.println("Invalid Arguments");
      return;
    }catch(NumberFormatException e){
      System.out.println("Invalid Input");
      return;
    }
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .65em">Finally, when the program is done, it should simply print "Complete" and exit. <mark>Don't forget to close any open files!</mark></p>
    <p style="font-size: .65em"><i>Already taken care of using<br>Try With Resources</i></p>
  </div>
</section><br>
---
type: "reveal"
hidden: true
---
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<br>
public class Throw{
<br>
  public static void main(String[] args){
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);
<br>
  }
}</code></pre>
</section>
<br>
<section>
  <h2>Checked Exception</h2>
	<pre class="" style="font-size: .40em">8j-except/Throw.java:11: error: unreported exception FileNotFoundException;
must be caught or declared to be thrown
      reader = new Scanner(new File(args[0]));
               ^
1 error</pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<br>
public class Throw{
<br>
  public static void main(String[] args){
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);
<br>
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<br>
public class Throw{
<br>
  public static void main(String[] args) <mark>throws FileNotFoundException</mark>{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);
<br>
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<mark>import java.io.FileNotFoundException;</mark>
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);
<br>
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);
<br>
  }
}</code></pre>
</section>
<br>
<section>
  <h2>Custom Exceptions</h2>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .43em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    double x = reader.nextDouble();
    double y = reader.nextDouble();
<br>
    if(y == 0.0){
      System.out.println("Error");
    }else{
      System.out.println(x / y);
    }
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .43em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    double x = reader.nextDouble();
    double y = reader.nextDouble();
<br>
    if(y == 0.0){
      <mark>System.out.println("Error");</mark>
    }else{
      System.out.println(x / y);
    }
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .43em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    double x = reader.nextDouble();
    double y = reader.nextDouble();
<br>
    if(y == 0.0){
      <mark>throw new ArithmeticException("Divide by Zero!");</mark>
    }else{
      System.out.println(x / y);
    }
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .43em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
<mark>import java.lang.ArithmeticException;</mark>
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    double x = reader.nextDouble();
    double y = reader.nextDouble();
<br>
    if(y == 0.0){
      <mark>throw new ArithmeticException("Divide by Zero!");</mark>
    }else{
      System.out.println(x / y);
    }
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .43em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.lang.ArithmeticException;
<br>
public class Throw{
<br>
  public static void main(String[] args) throws FileNotFoundException{
    Scanner reader;
<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    double x = reader.nextDouble();
    double y = reader.nextDouble();
<br>
    if(y == 0.0){
      throw new ArithmeticException("Divide by Zero!");
    }else{
      System.out.println(x / y);
    }
  }
}</code></pre>
</section>
<br>
---
type: "reveal"
hidden: true
---
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
    Scanner reader;
<br>
    try{
      reader = new Scanner(new File(args[0]))
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }finally{
      reader.close();
    }
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
    <mark>Scanner reader;</mark>
<br>
    try{
      reader = new Scanner(new File(args[0]))
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }finally{
      reader.close();
    }
  }
}</code></pre>
</section>
<br>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
    <mark>Scanner reader;</mark>
<br>
    try{
      <mark>reader = new Scanner(new File(args[0]))</mark>
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }finally{
      reader.close();
    }
  }
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
    <mark>Scanner reader;</mark>
<br>
    try{
      <mark>reader = new Scanner(new File(args[0]))</mark>
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }finally{
      <mark>reader.close();</mark>
    }
  }
}</code></pre>
</section>
<br>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
    Scanner reader;
<br>
    <mark>try(
      Scanner reader = new Scanner(new File(args[0]))
    ){</mark>
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }finally{
      reader.close();
    }
  }
}</code></pre>
</section>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
    <s>Scanner reader;</s>
<br>
    <mark>try(
      Scanner reader = new Scanner(new File(args[0]))
    ){</mark>
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }<s>finally{
      reader.close();
    }</s>
  }
}</code></pre>
</section>
<br>
<br>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.util.InputMismatchException;
import java.io.FileNotFoundException;
<br>
public class Resources{
<br>
  public static void main(String[] args){
<br>
    try(
      Scanner reader = new Scanner(new File(args[0]))
    ){
      int x = reader.nextInt();
      System.out.println(x + 5);
<br>
    }catch(InputMismatchException e){
      System.out.println("Error: Invalid Number Format!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }
  }
}</code></pre>
</section>
<br>
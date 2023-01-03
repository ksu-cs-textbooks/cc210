---
type: "reveal"
hidden: true
---<br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(new File(args[0]));
    }catch(FileNotFoundException e){
      System.out.println("Error: file not found!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
<mark>import java.io.File;</mark>
import java.io.FileNotFoundException;
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(<mark>new File(args[0])</mark>);
    }catch(FileNotFoundException e){
      System.out.println("Error: file not found!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
<mark>import java.nio.file.Paths;</mark>
import java.io.FileNotFoundException;
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(<mark>Paths.get(args[0])</mark>);
    }catch(FileNotFoundException e){
      System.out.println("Error: file not found!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
<mark>import java.io.FileNotFoundException;</mark>
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(Paths.get(args[0]));
    }catch(<mark>FileNotFoundException e</mark>){
      System.out.println("Error: file not found!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
<mark>import java.nio.file.NoSuchFileException;</mark>
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(Paths.get(args[0]));
    }catch(<mark>NoSuchFileException e</mark>){
      System.out.println("Error: file not found!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
import java.nio.file.NoSuchFileException;
<mark>import java.nio.file.InvalidPathException;</mark>
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(Paths.get(args[0]));
    }catch(NoSuchFileException e){
      System.out.println("Error: file not found!");
      return;
    <mark>}catch(InvalidPathException e){
      System.out.println("Error: invalid file path!");
      return;</mark>
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .33em"><code class="java">import java.util.Scanner;
import java.nio.file.Paths;
import java.nio.file.NoSuchFileException;
import java.nio.file.InvalidPathException;
import java.lang.ArrayIndexOutOfBoundsException;<br>
public class Read{<br>
  public static void main(String[] args){
    Scanner scanner;
    try{
      scanner = new Scanner(Paths.get(args[0]));
    }catch(NoSuchFileException e){
      System.out.println("Error: file not found!");
      return;
    }catch(InvalidPathException e){
      System.out.println("Error: invalid file path!");
      return;
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided, just read from System.in
      scanner = new Scanner(System.in);
    }<br>
    try(
      Scanner reader = scanner
    ){<br>
      /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */<br>
    }catch(Exception e){
      System.out.println("Exception: " + e);
    }
  }
}</code></pre>
</section><br>
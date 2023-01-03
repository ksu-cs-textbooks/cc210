---
type: "reveal"
hidden: true
---<br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">public class Write{
  public static void main(String[] args){<br>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">public class Write{
  public static void main(String[] args){
    <mark>try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){</mark><br><br>
    <mark>}catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br><br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java"><mark>import java.io.BufferedWriter;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      <mark>BufferedWriter</mark> writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br><br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
<mark>import java.nio.file.Files;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = <mark>Files</mark>.newBufferedWriter(Paths.get(args[0]));
    ){<br><br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
<mark>import java.nio.file.Paths;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(<mark>Paths</mark>.get(args[0]));
    ){<br><br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;<br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br><br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;<br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br>
      <mark>writer.write("Hello World");
      writer.newLine();</mark><br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;<br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br>
      writer.write("Hello World");
      writer.newLine();<br>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;
<mark>import java.lang.ArrayIndexOutOfBoundsException;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(<mark>args[0]</mark>));
    ){<br>
      writer.write("Hello World");
      writer.newLine();<br>
    <mark>}catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided
      System.out.println("Error: no arguments provided!");
      return;</mark>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.lang.ArrayIndexOutOfBoundsException;
<mark>import java.nio.file.InvalidPathException;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(<mark>Paths.get(args[0])</mark>);
    ){<br>
      writer.write("Hello World");
      writer.newLine();<br>
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided
      System.out.println("Error: no arguments provided!");
      return;
    <mark>}catch(InvalidPathException e){
      //path is invalid
      System.out.println("Error: invalid file path!");
      return;</mark>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.lang.ArrayIndexOutOfBoundsException;
import java.nio.file.InvalidPathException;
<mark>import java.io.IOException;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br>
      <mark>writer.write("Hello World");</mark>
      writer.newLine();<br>
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided
      System.out.println("Error: no arguments provided!");
      return;
    }catch(InvalidPathException e){
      //path is invalid
      System.out.println("Error: invalid file path!");
      return;
    <mark>}catch(IOException e){
      //cannot open file or error while writing
      System.out.println("Error: I/O error!");
      return;</mark>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.lang.ArrayIndexOutOfBoundsException;
import java.nio.file.InvalidPathException;
import java.io.IOException;
<mark>import java.lang.UnsupportedOperationException;</mark><br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = <mark>Files.newBufferedWriter(Paths.get(args[0]));</mark>
    ){<br>
      writer.write("Hello World");
      writer.newLine();<br>
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided
      System.out.println("Error: no arguments provided!");
      return;
    }catch(InvalidPathException e){
      //path is invalid
      System.out.println("Error: invalid file path!");
      return;
    }catch(IOException e){
      //cannot open file or error while writing
      System.out.println("Error: I/O error!");
      return;
    <mark>}catch(UnsupportedOperationException e){
      //unable to open the file for writing
      System.out.println("Error: unable to open file for writing!");
      return;</mark>
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br><br><br>
<section>
	<pre class="stretch" style="font-size: .276em"><code class="java">import java.io.BufferedWriter;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.lang.ArrayIndexOutOfBoundsException;
import java.nio.file.InvalidPathException;
import java.io.IOException;
import java.lang.UnsupportedOperationException;<br>
public class Write{
  public static void main(String[] args){
    try(
      BufferedWriter writer = Files.newBufferedWriter(Paths.get(args[0]));
    ){<br>
      writer.write("Hello World");
      writer.newLine();<br>
    }catch(ArrayIndexOutOfBoundsException e){
      //no arguments provided
      System.out.println("Error: no arguments provided!");
      return;
    }catch(InvalidPathException e){
      //path is invalid
      System.out.println("Error: invalid file path!");
      return;
    }catch(IOException e){
      //cannot open file or error while writing
      System.out.println("Error: I/O error!");
      return;
    }catch(UnsupportedOperationException e){
      //unable to open the file for writing
      System.out.println("Error: unable to open file for writing!");
      return;
    }catch(Exception e){
      //something went wrong
      System.out.println("Error: unknown error!");
      return;
    }
  }
}</code></pre>
</section><br>
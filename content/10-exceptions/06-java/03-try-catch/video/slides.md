---
type: "reveal"
hidden: true/images/
---<br>
<section>
	<img class="stretch plain" src="/cc210/images/10-except/8.4.handle.png">
</section><br>
<section>
	<img class="stretch plain" src="/cc210/images/10-except/8.4.try.png">
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);<br>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    <mark>try{</mark><br>
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);<br>
    <mark>}</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
    <mark>if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    }else{
      reader = new Scanner(System.in);
    }
    int x = reader.nextInt();
    System.out.println(x);</mark><br>
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      <mark>if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);</mark><br>
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }<mark>catch(Exception e){</mark><br>
    <mark>}</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(<mark>Exception e</mark>){<br>
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<mark>import java.lang.Exception;</mark><br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(<mark>Exception e</mark>){<br>
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.lang.Exception;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(Exception e){<br>
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.lang.Exception;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(Exception e){
      <mark>System.out.println("Error!");</mark>
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.lang.Exception;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(Exception e){
      System.out.println("Error!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.lang.Exception;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        <mark>reader = new Scanner(new File(args[0]));</mark>
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(Exception e){
      System.out.println("Error!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.lang.Exception;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(<mark>Exception e</mark>){
      System.out.println("Error!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.lang.Exception;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(<mark>FileNotFoundException e</mark>){
      System.out.println("Error!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<mark>import java.lang.Exception;</mark><br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println(<mark>"Error!"</mark>);
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
<mark>import java.io.FileNotFoundException;</mark><br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println(<mark>"Error: File Not Found!"</mark>);
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      <mark>int x = reader.nextInt();</mark>
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
<mark>import java.io.IOException;</mark><br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }<mark>catch(IOException e){
      System.out.println("Error: IO Exception!");
    }</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    <mark>}catch(IOException e){
      System.out.println("Error: IO Exception!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    <mark style="background-color: red">}catch(IOException e){
      System.out.println("Error: IO Exception!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }</mark>
  }
}</code></pre>
</section><br>
<section>
	<h2>Exception Hierarchy</h2>
	<img class="stretch plain" src="/cc210/images/10-except/8.7.j.3.filenotfound.png">
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    <mark style="background-color: red">}catch(IOException e){
      System.out.println("Error: IO Exception!");
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    <mark>}catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }</mark>
  }
}</code></pre>
</section><br><br>
<section>
	<pre class="stretch" style="font-size: .40em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = <mark>reader.nextInt();</mark>
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;
<mark>import java.util.InputMismatchException;</mark><br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }<mark>catch(InputMismatchException e){
      System.out.println("Error: Input Does Not Match Expected Format!");
    }</mark>
  }
}</code></pre>
</section><br>
<section>
	<pre class="stretch" style="font-size: .37em"><code class="java">import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException
import java.util.InputMismatchException;<br>
public class Example{<br>
  public static void main(String[] args){
    Scanner reader;<br>
    try{<br>
      if(args.length > 0){
        reader = new Scanner(new File(args[0]));
      }else{
        reader = new Scanner(System.in);
      }
      int x = reader.nextInt();
      System.out.println(x);<br>
    }catch(FileNotFoundException e){
      System.out.println("Error: File Not Found!");
    }catch(IOException e){
      System.out.println("Error: IO Exception!");
    }catch(InputMismatchException e){
      System.out.println("Error: Input Does Not Match Expected Format!");
    }
  }
}</code></pre>
</section><br>
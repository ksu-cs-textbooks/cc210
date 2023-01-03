---
type: "reveal"
hidden: true
---
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be greater than 0!");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }
    System.out.println("After Try");
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be greater than 0!");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }<mark>finally{
      System.out.println("Finally Block");
    }</mark>
    System.out.println("After Try");
  }
}</code></pre>
</section>
<br>
<section>
	<pre class="stretch" style="font-size: .45em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be greater than 0!");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      <mark>int x = reader.nextInt();</mark>
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      <mark>if(x &lt; 0){</mark>
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      <mark>}</mark>
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    <mark>}finally{</mark>
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      <mark>System.out.println("Finally Block");</mark>
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Finally Block</pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    <mark>}</mark>
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Finally Block</pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    <mark>System.out.println("After Try");</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Finally Block
After Try</pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  <mark>}</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Finally Block
After Try</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      <mark>int x = reader.nextInt();</mark>
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      <mark>if(x &lt; 0){</mark>
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        <mark>throw new IllegalArgumentException("Input must be...");</mark>
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    <mark>}catch(IllegalArgumentException e){</mark>
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      <mark>System.out.println(e.getMessage());</mark>
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Input must be...</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    <mark>}finally{</mark>
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Input must be...</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      <mark>System.out.println("Finally Block");</mark>
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Input must be...
Finally Block</pre>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    <mark>}</mark>
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Input must be...
Finally Block</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    <mark>System.out.println("After Try");</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Input must be...
Finally Block
After Try</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  <mark>}</mark>
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">-5</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Input must be...
Finally Block
After Try</pre>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      <mark>int x = reader.nextInt();</mark>
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }<mark>catch(InputMismatchException e){</mark>
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em"> </pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      <mark>System.out.println("Error: Must input an integer!");</mark>
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Error: Must input..</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    <mark>}finally{</mark>
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Error: Must input..</pre>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      <mark>System.out.println("Finally Block");</mark>
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Error: Must input..
Finally Block</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    <mark>}</mark>
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Error: Must input..
Finally Block</pre>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    <mark>System.out.println("After Try");</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Error: Must input..
Finally Block
After Try</pre>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">import java.util.Scanner;
import java.util.InputMismatchException;
import java.lang.IllegalArgumentException;
<br>
public class Finally{
<br>
  public static void main(String[] args){
    Scanner reader;
    reader = new Scanner(System.in);
    try{
      int x = reader.nextInt();
      if(x &lt; 0){
        throw new IllegalArgumentException("Input must be...");
      }
    }catch(InputMismatchException e){
      System.out.println("Error: Must input an integer!");
    }catch(IllegalArgumentException e){
      System.out.println(e.getMessage());
    }finally{
      System.out.println("Finally Block");
    }
    System.out.println("After Try");
  }
}</code></pre>
  </div>
  <div style="width: 30%">
    <p>Input:</p>
    <pre style="font-size: 1em">abc</pre>
    <p>Output:</p>
    <pre style="font-size: .5em">Error: Must input..
Finally Block
After Try</pre>
  </div>
</section>
<br>
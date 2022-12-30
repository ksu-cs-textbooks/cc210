---
type: "reveal"
hidden: true
---

<section>
  <h3>Problem Statement</h3>
  <blockquote class="stretch" style="text-align: left">Write a program that accepts a positive integer that represents a year, and prints whether that year is a leap year or not. If the year is a leap year, it should print output similar to "2000 is a Leap Year". If not, it should print output similar to "2001 is not a Leap Year".</blockquote>
</section>
<section>
  <h3>Leap Years</h3>
  <blockquote class="stretch" style="text-align: left">Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400. For example, the years 1700, 1800, and 1900 are not leap years, but the year 2000 is. - USNO</blockquote>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>public class Example{
  public static void main(String[] args){<br>
  }
}</mark></code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">// Load required classes
<mark>import java.util.Scanner;
import java.io.File;</mark><br>
public class Example{
  public static void main(String[] args){<br>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">// Load required classes
import java.util.Scanner;
import java.io.File;<br>
public class Example{
  public static void main(String[] args){
    // Scanner variable
    <mark>Scanner reader;</mark><br>
    // If an argument is present,
    // we are reading from a file
    // specified in args[0]
    <mark>if(args.length > 0){
      reader = new Scanner(new File(args[0]));</mark>
    // If no argument, read from System.in
    <mark>}else{
      reader = new Scanner(System.in);
    }</mark><br>
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
  }
}</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">// Load required classes
import java.util.Scanner;
import java.io.File;<br>
public class Example{
  public static void main(String[] args) <mark>throws Exception</mark>{
    // Scanner variable
    Scanner reader;<br>
    // If an argument is present,
    // we are reading from a file
    // specified in args[0]
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    // If no argument, read from System.in
    }else{
      reader = new Scanner(System.in);
    }<br>
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
  }
}</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">// Load required classes
import java.util.Scanner;
import java.io.File;<br>
public class Example{
  public static void main(String[] args) throws Exception{
    // Scanner variable
    Scanner reader;<br>
    // If an argument is present,
    // we are reading from a file
    // specified in args[0]
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    // If no argument, read from System.in
    }else{
      reader = new Scanner(System.in);
    }<br>
    <mark>/* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */</mark>
  }
}</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive integer that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive <mark>integer that represents a year</mark>...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java"><mark>int year = reader.nextInt();</mark>
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a positive <mark>integer that represents a year</mark>...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a <mark>positive integer</mark> that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
<mark>if(year <= 0){
  System.out.println("Error");
}else{<br>
}</mark>
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that accepts a <mark>positive integer</mark> that represents a year...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{<br>
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Every year that is exactly divisible by four is a leap year, except...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{<br>
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Every year that is exactly <mark>divisible by four is a leap year</mark>, except...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  <mark>if(year % 4 == 0){
    //divisible by 4
  }else{
    //not divisible by 4
    System.out.println("no");
  }</mark>
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Every year that is exactly <mark>divisible by four is a leap year</mark>, except...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...except for years that are exactly divisible by 100, but...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...except for years that are <mark>exactly divisible by 100</mark>, but...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    <mark>if(year % 100 == 0){
      //divisible by 4 and 100
      System.out.println("no");
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }</mark>
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...except for years that are <mark>exactly divisible by 100</mark>, but...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      System.out.println("no");
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      System.out.println("no");
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are <mark>exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      <mark>System.out.println("no");</mark>
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are <mark>exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      <mark>if(year % 400 == 0){
        //divisible by 4 and 100 and 400
        System.out.println("yes");
      }else{
        //divisible by 4 and 100 not 400
        System.out.println("no");
      }</mark>
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...but these centurial years are leap years if they are <mark>exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      if(year % 400 == 0){
        //divisible by 4 and 100 and 400
        System.out.println("yes");
      }else{
        //divisible by 4 and 100 not 400
        System.out.println("no");
      }
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java"><mark>int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{</mark>
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      if(year % 400 == 0){
        //divisible by 4 and 100 and 400
        System.out.println("yes");
      }else{
        //divisible by 4 and 100 not 400
        System.out.println("no");
      }
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...<mark>positive integer that represents a year</mark>...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  <mark>if(year % 4 == 0){</mark>
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      if(year % 400 == 0){
        //divisible by 4 and 100 and 400
        System.out.println("yes");
      }else{
        //divisible by 4 and 100 not 400
        System.out.println("no");
      }
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  <mark>}else{</mark>
    //not divisible by 4
    <mark>System.out.println("no");</mark>
  <mark>}</mark>
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly <mark>divisible by four is a leap year</mark>, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    <mark>if(year % 100 == 0){</mark>
      //divisible by 4 and 100
      if(year % 400 == 0){
        //divisible by 4 and 100 and 400
        System.out.println("yes");
      }else{
        //divisible by 4 and 100 not 400
        System.out.println("no");
      }
    <mark>}else{</mark>
      //divisible by 4 but not 100
      <mark>System.out.println("yes");</mark>
    <mark>}</mark>
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, <mark>except for years that are exactly divisible by 100</mark>, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      <mark>if(year % 400 == 0){</mark>
        //divisible by 4 and 100 and 400
        <mark>System.out.println("yes");</mark>
      <mark>}else{</mark>
        //divisible by 4 and 100 not 400
        <mark>System.out.println("no");</mark>
      <mark>}</mark>
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, <mark>but these centurial years are leap years if they are exactly divisible by 400.</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="java">int year = reader.nextInt();
if(year <= 0){
  System.out.println("Error");
}else{
  if(year % 4 == 0){
    //divisible by 4
    if(year % 100 == 0){
      //divisible by 4 and 100
      if(year % 400 == 0){
        //divisible by 4 and 100 and 400
        System.out.println("yes");
      }else{
        //divisible by 4 and 100 not 400
        System.out.println("no");
      }
    }else{
      //divisible by 4 but not 100
      System.out.println("yes");
    }
  }else{
    //not divisible by 4
    System.out.println("no");
  }
}
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...positive integer that represents a year...<br>Every year that is exactly divisible by four is a leap year, except for years that are exactly divisible by 100, but these centurial years are leap years if they are exactly divisible by 400.</p>
  </div>
</section>

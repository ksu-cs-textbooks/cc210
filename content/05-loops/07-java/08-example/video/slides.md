---
type: "reveal"
hidden: true
---
<br>
<section>
  <h3>Problem Statement</h3>
  <blockquote class="stretch" style="text-align: left; font-size: .9em">Write a program that will accept a series of integers from the user, one per line. It will continue to accept integers from the user until the user inputs 0. If the user inputs a negative number, the program should print "Error! Positive Integers Only" and continue to receive input. Once the user inputs 0, the program should print the sum and average of the positive integers input by the user.</blockquote>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch"><code class="java">
    </code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that will accept a series of integers from the user, one per line...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">// Load required classes
import java.util.Scanner;
import java.io.File;
<br>
public class Example{
  public static void main(String[] args) throws Exception{
    // Scanner variable
    Scanner reader;
<br>
    // If an argument is present,
    // we are reading from a file
    // specified in args[0]
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    // If no argument, read from System.in
    }else{
      reader = new Scanner(System.in);
    }
<br>
    <mark>/* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */</mark>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that will accept a series of integers from the user, one per line...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that will accept a series of integers from the user, one per line...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>while(){
<br>
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that will accept a series of integers from the user, one per line...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(){
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that will accept a <mark>series of integers</mark> from the user, <mark>one per line</mark>...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(){
  <mark>int x = reader.nextInt();</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">Write a program that will accept a <mark>series of integers</mark> from the user, <mark>one per line</mark>...</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(){
  int x = reader.nextInt();
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">It will continue to accept integers from the user <mark>until the user inputs 0</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(<mark>x != 0</mark>){
  int x = reader.nextInt();
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">It will continue to accept integers from the user <mark>until the user inputs 0</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>int x = 0;</mark>
while(x != 0){
  <mark><s>int</s></mark> x = reader.nextInt();
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">It will continue to accept integers from the user <mark>until the user inputs 0</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = <mark>1</mark>;
while(x != 0){
  x = reader.nextInt();
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">It will continue to accept integers from the user <mark>until the user inputs 0</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
while(x != 0){
  x = reader.nextInt();
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">If the user <mark>inputs a negative number</mark>, the program should print "Error! Positive Integers Only" and <mark>continue to receive input</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
while(x != 0){
  x = reader.nextInt();
  <mark>if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }</mark>
  //logic here
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">If the user <mark>inputs a negative number</mark>, the program should print "Error! Positive Integers Only" and <mark>continue to receive input</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  //logic here
}
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...the program should print the <mark>sum</mark> and average of the positive integers input by the user.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
<mark>int sum = 0;</mark>
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  <mark>sum += x;</mark>
}
<mark>System.out.println("Sum: " + sum);</mark>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...the program should print the <mark>sum</mark> and average of the positive integers input by the user.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
}
System.out.println("Sum: " + sum);
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...the program should print the sum and <mark>average</mark> of the positive integers input by the user.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
<mark>int count = 0;</mark>
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  <mark>count++;</mark>
}
System.out.println("Sum: " + sum);
<mark>System.out.println("Average: " + (double)sum / count);</mark>
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...the program should print the sum and <mark>average</mark> of the positive integers input by the user.</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
  <p style="font-size: .7em">...the program should print the sum and average of the positive integers input by the user.</p>
  </div>
</section>
<section>
  <h1>Logic Bug!</h1>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>int x = 1;
int sum = 0;
int count = 0;</mark>
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p><mark>x = 1</mark></p>
   <p><mark>sum = 0</mark></p>
   <p><mark>count = 0</mark></p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
<mark>while(x != 0){</mark>
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 1</p>
   <p>sum = 0</p>
   <p>count = 0</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  <mark>x = reader.nextInt();</mark>
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p><mark>x = 3</mark></p>
   <p>sum = 0</p>
   <p>count = 0</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  <mark>if(x < 0){</mark>
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 3</p>
   <p>sum = 0</p>
   <p>count = 0</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  <mark>sum += x;
  count++;</mark>
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 3</p>
   <p><mark>sum = 3</mark></p>
   <p><mark>count = 1<mark></p>
  </div>
</section>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
<mark>while(x != 0){</mark>
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 3</p>
   <p>sum = 3</p>
   <p>count = 1</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  <mark>x = reader.nextInt();</mark>
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p><mark>x = 1</mark></p>
   <p>sum = 3</p>
   <p>count = 1</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  <mark>if(x < 0){</mark>
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 1</p>
   <p>sum = 3</p>
   <p>count = 1</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  <mark>sum += x;
  count++;</mark>
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 1</p>
   <p><mark>sum = 4</mark></p>
   <p><mark>count = 2<mark></p>
  </div>
</section>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
<mark>while(x != 0){</mark>
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 1</p>
   <p>sum = 4</p>
   <p>count = 2</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  <mark>x = reader.nextInt();</mark>
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p><mark>x = 0</mark></p>
   <p>sum = 4</p>
   <p>count = 2</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  <mark>if(x < 0){</mark>
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 0</p>
   <p>sum = 4</p>
   <p>count = 2</p>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  <mark>sum += x;
  count++;</mark>
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 0</p>
   <p><mark>sum = 4</mark></p>
   <p><mark>count = 3<mark></p>
  </div>
</section>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
<mark>while(x != 0){</mark>
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 0</p>
   <p>sum = 4</p>
   <p>count = 3</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
<mark>System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);</mark>
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Variables</h4>
   <p>x = 0</p>
   <p>sum = 4</p>
   <p>count = 3</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  <mark>if(x != 0){
    sum += x;
    count++;
  }</mark>
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>If-Then</h4>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = 1;
int sum = 0;
int count = 0;
while(x != 0){
  x = reader.nextInt();
  <mark>if(x == 0){
    break;
  }</mark>
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }
  sum += x;
  count++;
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Break</h4>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = <mark>reader.nextInt()</mark>;
int sum = 0;
int count = 0;
while(x != 0){
  if(x < 0){
    System.out.println("Error! Positive Integers Only");
  }<mark>else{
    sum += x;
    count++;
  }
  x = reader.nextInt();</mark>
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>Rearrange</h4>
  </div>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int x = <mark>0</mark>;
int sum = 0;
int count = 0;
while(<mark>true</mark>){
  x = reader.nextInt();
  <mark>if(x == 0){
    break;
  }else</mark> if(x < 0){
    System.out.println("Error! Positive Integers Only");
    continue;
  }<mark>else{
    sum += x;
    count++;
  }</mark>
}
System.out.println("Sum: " + sum);
System.out.println("Average: " + (double)sum / count);
</code></pre>
  </div>
  <div style="width: 30%">
   <h4>If-Else If</h4>
  </div>
</section>
<section>
  <h3>Many Different Solutions</h3>
  <p>Choose one and work through the code, recording variable values on paper to confirm that it performs properly</p>
</section>
<br>
---
type: "reveal"
hidden: true
---
<br>
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
    <p>Skeleton</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Handle Input</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
<br>
<mark>if(numAssignments > 0){
<br>
}else{
  System.out.println("Invalid Input!");
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Handle Input</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
<br>
if(numAssignments > 0){
<br>
  <mark>int[] scores = new int[numAssignments];
  double[] weights = new double[numAssignments];</mark>
<br>
}else{
  System.out.println("Invalid Input!");
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Create Arrays</p>
  </div>
</section>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
<br>
if(numAssignments > 0){
<br>
  int[] scores = new int[numAssignments];
  double[] weights = new double[numAssignments];
<br>
  <mark>for(int i = 0; i < numAssignments; i++){
    scores[i] = reader.nextInt();
    weights[i] = reader.nextDouble();
  }</mark>
<br>
}else{
  System.out.println("Invalid Input!");
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Fill Arrays</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
<br>
if(numAssignments > 0){
<br>
  int[] scores = new int[numAssignments];
  double[] weights = new double[numAssignments];
<br>
  for(int i = 0; i < numAssignments; i++){
    scores[i] = reader.nextInt();
    weights[i] = reader.nextDouble();
  }
<br>
  <mark>double sum = 0.0;
  for(double d : weights){
    sum += d;
  }
<br>
  if(sum == 1.0){
<br>
  }else{
    System.out.println("Error! Weights do not add...");
  }</mark>
<br>
}else{
  System.out.println("Invalid Input!");
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Check Weights</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
<br>
if(numAssignments > 0){
<br>
  int[] scores = new int[numAssignments];
  double[] weights = new double[numAssignments];
  for(int i = 0; i < numAssignments; i++){
    scores[i] = reader.nextInt();
    weights[i] = reader.nextDouble();
  }
<br>
  double sum = 0.0;
  for(double d : weights){
    sum += d;
  }
  if(sum == 1.0){
<br>
    <mark>double totalScore = 0.0;
    for(int j = 0; j < numAssignments; j++){
      totalScore += scores[j] * weights[j];
    }
    System.out.println(totalScore);</mark>
<br>
  }else{
    System.out.println("Error! Weights do not add...");
  }
}else{
  System.out.println("Invalid Input!");
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Calculate Score</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">int numAssignments = reader.nextInt();
<br>
if(numAssignments > 0){
<br>
  int[] scores = new int[numAssignments];
  double[] weights = new double[numAssignments];
  for(int i = 0; i < numAssignments; i++){
    scores[i] = reader.nextInt();
    weights[i] = reader.nextDouble();
  }
<br>
  double sum = 0.0;
  for(double d : weights){
    sum += d;
  }
  if(sum == 1.0){
<br>
    double totalScore = 0.0;
    for(int j = 0; j < numAssignments; j++){
      totalScore += scores[j] * weights[j];
    }
    System.out.println(totalScore);
<br>
  }else{
    System.out.println("Error! Weights do not add...");
  }
}else{
  System.out.println("Invalid Input!");
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Done!</p>
  </div>
</section>
<br>
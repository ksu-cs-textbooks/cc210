---
type: "reveal"
hidden: true
---
<br>
<section>
	<h2>Problem Statement</h2>
</section>
<section>
	<p style="font-size: 0.5em">Write a program that will calculate weighted grades for students in a college course. The input will be given in a comma-delimited format. The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
	<p style="font-size: 0.5em">Each subsequent line of input will contain information for a student. The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, separated by commas. Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
	<p style="font-size: 0.5em">It is guaranteed that at least two lines of input will be provided, the first containing the weights and at least one additional line containing data for a student. In addition, it is guaranteed that each line of input will contain the same number of parts.</p>
	<p style="font-size: 0.5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
</section>
<section>
	<h2>Yikes!</h2>
	<p>Let's break it down into smaller parts</p>
</section>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">// Load required classes
import java.util.Scanner;
import java.io.File;
<br>
public class Example{
<br>
  public static void main(String[] args) throws Exception{
    // Scanner variable
    Scanner reader;
<br>
    // If an argument is present, read from a file
    // specified in args[0]
    if(args.length > 0){
      reader = new Scanner(new File(args[0]));
    // If no argument, read from System.in
    }else{
      reader = new Scanner(System.in);
    }
<br>
    /* -=-=-=-=- MORE CODE GOES HERE -=-=-=-=- */
<br>
  }
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p>Skeleton</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The first line</mark> will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>String weightLine = reader.nextLine();</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The first line</mark> will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line <mark>will contain a number of weights</mark> as floating-point numbers, <mark>separated by commas</mark>. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
<mark>String[] weightParts = weightLine.split(",");</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line <mark>will contain a number of weights</mark> as floating-point numbers, <mark>separated by commas</mark>. The first entry should be ignored.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights as floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
<mark>double[] weights = new double[weightParts.length];</mark>
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights as floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights</mark> as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
<mark>for(int i = 0; i &lt; weights.length; i++){
  weights[i] = weightParts[i];
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain <mark>a number of weights</mark> as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = 0; i &lt; weights.length; i++){
  weights[i] = <mark>weightParts[i];</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as <mark>floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = 0; i &lt; weights.length; i++){
  weights[i] = <mark>Double.parseDouble(weightParts[i]);</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as <mark>floating-point numbers</mark>, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = 0; i &lt; weights.length; i++){
  weights[i] = Double.parseDouble(weightParts[i]);
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. <mark>The first entry should be ignored.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = <mark>0</mark>; i &lt; weights.length; i++){
  weights[i] = Double.parseDouble(weightParts[i]);
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. <mark>The first entry should be ignored.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = <mark>1</mark>; i &lt; weights.length; i++){
  weights[i] = Double.parseDouble(weightParts[i]);
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. <mark>The first entry should be ignored.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = 1; i &lt; weights.length; i++){
  weights[i] = Double.parseDouble(weightParts[i]);
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first line will contain a number of weights as floating-point numbers, separated by commas. The first entry should be ignored.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">
<br>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>Each subsequent line of input</mark> will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java"><mark>while(reader.hasNext()){
<br>
}</mark>
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>Each subsequent line of input</mark> will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent <mark>line of input will contain information for a student</mark>. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  <mark>String line = reader.nextLine();</mark>
<br>
  <mark>// parse the input</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent <mark>line of input will contain information for a student</mark>. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
<br>
  // parse the input
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, <mark>or by a blank line when input is provided via the terminal.</mark></p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  <mark>if(line.length() == 0){</mark>
    <mark>break;</mark>
  <mark>}</mark>
<br>
  // parse the input
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, <mark>or by a blank line when input is provided via the terminal.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  // parse the input
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Each subsequent line of input will contain information for a student. ... Input will be terminated by the end of the input file, or by a blank line when input is provided via the terminal.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  // parse the input
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, separated by commas.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  // parse the input
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, <mark>separated by commas.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  <mark>String[] parts = line.split(",");</mark>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an integer value, <mark>separated by commas.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. <mark>The rest of the line will contain that student’s scores on each assignment as an integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  <mark>for(int j = 1; j &lt; parts.length; j++){
    parts[j];
  }</mark>
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. <mark>The rest of the line will contain that student’s scores on each assignment as an integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  for(int j = 1; j &lt; parts.length; j++){
    parts[j];
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an <mark>integer value</mark>, separated by commas.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  for(int j = 1; j &lt; parts.length; j++){
    <mark>Integer.parseInt(parts[j]);</mark>
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The first entry on that line will contain that student’s name. The rest of the line will contain that student’s scores on each assignment as an <mark>integer value</mark>, separated by commas.</p>
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
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  for(int j = 1; j &lt; parts.length; j++){
    Integer.parseInt(parts[j]);
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate weighted grades for students in a college course.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  for(int j = 1; j &lt; parts.length; j++){
    Integer.parseInt(parts[j]);
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  for(int j = 1; j &lt; parts.length; j++){
    Integer.parseInt(parts[j]);
  }
<br>
}
</code></pre>
  </div>
	<div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.<p>
		<p style="font-size: .5em; font-family: monospace">Total =<br>Sum(Score[i] * Weight[i])</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  for(int j = 1; j &lt; parts.length; j++){
    <mark>weights[j] * Integer.parseInt(parts[j]);</mark>
  }
<br>
}
</code></pre>
  </div>
	<div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.<p>
		<p style="font-size: .5em; font-family: monospace">Total =<br>Sum(Score[i] * Weight[i])</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  <mark>double totalScore = 0.0;</mark>
  for(int j = 1; j &lt; parts.length; j++){
    <mark>totalScore += </mark>weights[j] * Integer.parseInt(parts[j]);
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">Write a program that will calculate <mark>weighted grades</mark> for students in a college course.<p>
		<p style="font-size: .5em; font-family: monospace">Total =<br>Sum(Score[i] * Weight[i])</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The program should output</mark> the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  <mark>System.out.println();</mark>
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em"><mark>The program should output</mark> the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<br>
<br>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  <mark>...();</mark>
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...();
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be <mark>formatted to be exactly 5 characters wide</mark>, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(<mark>String.format()</mark>);
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be <mark>formatted to be exactly 5 characters wide</mark>, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format());
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the <mark>student’s name, followed by a colon, and a space,</mark> and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format("<mark>%s: </mark>", <mark>parts[0]</mark>));
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the <mark>student’s name, followed by a colon, and a space,</mark> and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format("%s: ", parts[0]));
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, <mark>and then the student’s score.</mark> The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format("%s: <mark>%f</mark>", parts[0], <mark>totalScore</mark>));
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, <mark>and then the student’s score.</mark> The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format("%s: %f", parts[0], totalScore));
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. <mark>The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format("%s: <mark>%5.2f</mark>", parts[0], totalScore));
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. <mark>The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</mark></p>
  </div>
</section>
<br>
<section>
  <div style="float: right; width: 70%">
    <pre class="stretch" style="font-size: .37em"><code class="java">while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  ...(String.format("%s: %5.2f", parts[0], totalScore));
<br>
}
</code></pre>
  </div>
  <div style="width: 30%">
    <p style="font-size: .5em">The program should output the student’s name, followed by a colon, and a space, and then the student’s score. The score should be formatted to be exactly 5 characters wide, with exactly two characters after the decimal point.</p>
  </div>
</section>
<br>
<section>
    <pre class="stretch" style="font-size: .44em"><code class="java">String weightLine = reader.nextLine();
String[] weightParts = weightLine.split(",");
<br>
double[] weights = new double[weightParts.length];
<br>
for(int i = 1; i &lt; weights.length; i++){
  weights[i] = Double.parseDouble(weightParts[i]);
}
<br>
while(reader.hasNext()){
  String line = reader.nextLine();
  if(line.length() == 0){
    break;
  }
<br>
  String[] parts = line.split(",");
<br>
  double totalScore = 0.0;
  for(int j = 1; j &lt; parts.length; j++){
    totalScore += weights[j] * Integer.parseInt(parts[j]);
  }
<br>
  System.out.println(String.format("%s: %5.2f", parts[0], totalScore));
<br>
}</code></pre>
</section>
<br>
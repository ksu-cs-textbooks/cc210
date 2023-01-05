---
type: "reveal"
hidden: true
---
<section>
    <img class="plain stretch" style="" src="/images/13-inherit/12.7.j.uml.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Vehicle{<br>
  private String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  public Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public String describe(){
    return "";
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Vehicle{<br>
  <mark>private</mark> String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  <mark>public</mark> Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public String describe(){
    return "";
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Vehicle{<br>
  <mark>protected</mark> String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  <mark>protected</mark> Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public String describe(){
    return "";
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Vehicle{<br>
  protected String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  protected Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public String describe(){
    return "";
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public <mark>abstract</mark> class Vehicle{<br>
  protected String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  protected Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public <mark>abstract</mark> String describe(){
    return "";
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public abstract class Vehicle{<br>
  protected String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  protected Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public abstract String describe()<mark>{
    return "";
  }</mark><br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public abstract class Vehicle{<br>
  protected String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  protected Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public abstract String describe()<mark>;</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public abstract class Vehicle{<br>
  protected String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  protected Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }<br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public abstract String describe();<br>
}</code></pre>
  </div>
</section><br>
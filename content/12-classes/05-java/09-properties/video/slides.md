---
type: "reveal"
hidden: true
---
<section>
  <div style="float: right; width: 50%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.9.propertyuml.property.png">
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.9.propertyuml.property.png">
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  <mark>private</mark> String name;<br>
  public Property(){
    name = "";
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.9.propertyuml.property.png">
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  <mark>public String getName(){
    return name;
  }</mark><br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.9.propertyuml.property.png">
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  <mark>public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.9.propertyuml.property.png">
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String <mark>getName</mark>(){
    return name;
  }<br>
  public void <mark>setName</mark>(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.6.j.9.propertyuml.property.png">
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Main{
  public static void main(String[] args){
    Property prop = new Property();
    String name = prop.getName();
    System.out.println(name);
    prop.setName("test");
    System.out.println(prop.getName());
  }
}</code></pre>
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Main{
  public static void main(String[] args){
    Property prop = new Property();
    String name = <mark>prop.getName()</mark>;
    System.out.println(name);
    prop.setName("test");
    System.out.println(prop.getName());
  }
}</code></pre>
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Main{
  public static void main(String[] args){
    Property prop = new Property();
    String name = prop.getName();
    System.out.println(name);
    <mark>prop.setName("test")</mark>;
    System.out.println(prop.getName());
  }
}</code></pre>
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Main{
  public static void main(String[] args){
    Property prop = new Property();
    String name = prop.getName();
    System.out.println(name);
    prop.setName("test");
    System.out.println(<mark>prop.getName()</mark>);
  }
}</code></pre>
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Main{
  public static void main(String[] args){
    Property prop = new Property();
    String name = prop.getName();
    System.out.println(name);
    prop.setName("test");
    System.out.println(prop.getName());
  }
}</code></pre>
  </div>
  <div style="width: 50%">
    <pre class="stretch" style="font-size: .35em"><code class="java">public class Property{
  private String name;<br>
  public Property(){
    name = "";
  }<br>
  public String getName(){
    return name;
  }<br>
  public void setName(String a_name){
    if(a_name.length() == 0){
      throw new IllegalArgumentException(
        "Name cannot be an empty string!");
    }
    this.name = a_name;
  }<br>
}</code></pre>
  </div>
</section><br>
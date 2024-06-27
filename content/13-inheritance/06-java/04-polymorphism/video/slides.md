---
type: "reveal"
hidden: true
---
<section>
    <img class="plain stretch" style="" src="/cc210/images/13-inherit/12.7.j.uml.png">
</section><br>
<section>
  <pre class="stretch" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
  <img class="plain" style="height: 400px" src="/cc210/images/13-inherit/12.7.j.4.test1.png">
</section><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
Car
I'm a sedan
Moving
10.0</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    <mark>Vehicle plane = new Airplane("Plane", 123, 45);</mark>
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
Car
I'm a sedan
Moving
10.0</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    <mark>System.out.println(plane.getName());</mark>
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md"><mark>Plane</mark>
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
Car
I'm a sedan
Moving
10.0</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    <mark>System.out.println(plane.describe());</mark>
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
<mark>I am an airplane with a wingspan of 123.000000 and capacity 45</mark>
Landing gear up
Moving
Landing gear down
10.0
Car
I'm a sedan
Moving
10.0</code></pre>
</section><br><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    <mark>System.out.println(plane.move(10));</mark><br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
<mark>Landing gear up
Moving
Landing gear down
10.0</mark>
Car
I'm a sedan
Moving
10.0</code></pre>
</section><br><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    <mark>Vehicle car = new Car("Car", 4);</mark>
    System.out.println(car.getName());
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
Car
I'm a sedan
Moving
10.0</code></pre>
</section><br><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    <mark>System.out.println(car.getName());</mark>
    System.out.println(car.describe());
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
<mark>Car</mark>
I'm a sedan
Moving
10.0</code></pre>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    <mark>System.out.println(car.describe());</mark>
    System.out.println(car.move(10));
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
Car
<mark>I'm a sedan</mark>
Moving
10.0</code></pre>
</section><br><br><br>
<section>
  <pre class="stretch" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle plane = new Airplane("Plane", 123, 45);
    System.out.println(plane.getName());
    System.out.println(plane.describe());
    System.out.println(plane.move(10));<br>
    Vehicle car = new Car("Car", 4);
    System.out.println(car.getName());
    System.out.println(car.describe());
    <mark>System.out.println(car.move(10));</mark>
  }
}</code></pre>
<pre class="" style="font-size: .45em; height: 450px"><code style="height: 450px" class="md">Plane
I am an airplane with a wingspan of 123.000000 and capacity 45
Landing gear up
Moving
Landing gear down
10.0
Car
I'm a sedan
<mark>Moving
10.0</mark></code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle car = new Car("Car", 4);
    System.out.println(car.honk_horn());
  }
}</code></pre>
</section><br><br>
<section>
  <pre class="" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle car = <mark>new Car("Car", 4);</mark>
    System.out.println(car.honk_horn());
  }
}</code></pre>
</section><br><br>
<section>
  <pre class="" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    <mark>Vehicle car</mark> = new Car("Car", 4);
    System.out.println(car.honk_horn());
  }
}</code></pre>
</section><br><br>
<section>
  <pre class="" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle car = new Car("Car", 4);
    System.out.println(<mark>car.honk_horn()</mark>);
  }
}</code></pre>
</section><br><br>
<section>
  <pre class="" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle car = new Car("Car", 4);
    System.out.println(<mark>car.honk_horn()</mark>);
  }
}</code></pre>
  <img class="plain" style="height: 400px" src="/cc210/images/13-inherit/12.7.j.vehicle.png">
</section><br><br><br>
<section>
  <pre class="" style="font-size: .42em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle car = new Car("Car", 4);
    System.out.println(<mark style="background-color: red">car.honk_horn()</mark>);
  }
}</code></pre>
  <img class="plain" style="height: 400px" src="/cc210/images/13-inherit/12.7.j.4.error1.png">
</section><br>
<section>
  <h3>Rules</h3>
  <ol>
    <li>Store any child class within parent class variable</li>
    <li>Use attributes and methods based on data type of variable, regardless of type stored</li>
    <li>Overriden methods will use code in child class even when stored as parent data type</li>
  </ol>
</section><br><br>
<section>
  <pre class="stretch" style="font-size: .38em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle[] array = new Vehicle[3];
    array[0] = new Airplane("Plane", 123, 45);
    array[1] = new Car("Car", 4);
    array[2] = new Truck("Truck", 157);<br>
    for(Vehicle v : array){
      System.out.println(v.getName());
      System.out.println(v.describe());
      System.out.println(v.move(10));
    }
  }
}</code></pre>
<img class="plain" style="height: 450px" src="/cc210/images/13-inherit/12.7.j.4.test2.png">
</section><br>
---
type: "reveal"
hidden: true
---
<section>
    <img class="plain stretch" style="" src="/cc210/images/13-inherit/12.7.j.uml.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.vehicle.png">
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
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Vehicle{<br>
  private String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  <mark>public Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }</mark><br>
  public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }<br>
  public String describe(){
    return "";
  }<br>
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.vehicle.png">
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
  <mark>public double move(double distance){
    System.out.println("Moving");
    return distance / this.speed;
  }</mark><br>
  <mark>public String describe(){
    return "";
  }</mark><br>
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    this.name = name;
    this.wingspan = wingspan;
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br>
<section>
    <img class="plain stretch" style="" src="/cc210/images/13-inherit/12.7.j.2.error.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    <mark style="background-color: red">this.name = name;</mark>
    this.wingspan = wingspan;
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Vehicle{<br>
  private String name;
  public double speed;<br>
  public String getName(){ return this.name; }<br>
  <mark>public Vehicle(String name){
    this.name = name;
    this.speed = 1.0;
  }</mark><br>
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
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    <mark style="background-color: red">this.name = name;</mark>
    this.wingspan = wingspan;
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    <mark style="background-color: green">super(name);</mark>
    this.wingspan = wingspan;
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    this.wingspan = wingspan;
    <mark style="background-color: red">super(name);</mark>
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    this.wingspan = wingspan;
    <s><mark style="background-color: red">super(name);</mark></s>
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    <mark style="background-color: green">super(name);</mark>
    this.wingspan = wingspan;
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }<br>
  public void landing_gear(boolean set){
    if(set){
      System.out.println("Landing gear down");
    }else{
      System.out.println("Landing gear up");
    }
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }<br>
  public void landing_gear(boolean set){
    if(set){
      System.out.println("Landing gear down");
    }else{
      System.out.println("Landing gear up");
    }
  }<br>
  @Override
  public double move(double distance){
    this.landing_gear(false);
    System.out.println("Moving");
    this.landing_gear(true);
    return distance / this.speed;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }<br>
  public void landing_gear(boolean set){
    if(set){
      System.out.println("Landing gear down");
    }else{
      System.out.println("Landing gear up");
    }
  }<br>
  @Override
  <mark>public double move(double distance){</mark>
    this.landing_gear(false);
    System.out.println("Moving");
    this.landing_gear(true);
    return distance / this.speed;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }<br>
  public void landing_gear(boolean set){
    if(set){
      System.out.println("Landing gear down");
    }else{
      System.out.println("Landing gear up");
    }
  }<br>
  <mark>@Override</mark>
  public double move(double distance){
    this.landing_gear(false);
    System.out.println("Moving");
    this.landing_gear(true);
    return distance / this.speed;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }<br>
  public void landing_gear(boolean set){
    if(set){
      System.out.println("Landing gear down");
    }else{
      System.out.println("Landing gear up");
    }
  }<br>
  @Override
  public double move(double distance){
    this.landing_gear(false);
    System.out.println("Moving");
    this.landing_gear(true);
    return distance / this.speed;
  }<br>
  <mark>@Override
  public String describe(){</mark>
    return String.format("I am an airplane with a wingspan of
            %f and capacity %d", this.wingspan, this.capacity);
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .34em"><code class="java">public class Airplane extends Vehicle{<br>
  private double wingspan;
  private int capacity;<br>
  public Airplane(String name, double wingspan, int capacity){
    super(name);
    this.wingspan = wingspan;
    this.capacity = capacity;
  }<br>
  public void landing_gear(boolean set){
    if(set){
      System.out.println("Landing gear down");
    }else{
      System.out.println("Landing gear up");
    }
  }<br>
  @Override
  public double move(double distance){
    this.landing_gear(false);
    System.out.println("Moving");
    this.landing_gear(true);
    return distance / this.speed;
  }<br>
  @Override
  public String describe(){
    return String.format("I am an airplane with a wingspan of
            %f and capacity %d", this.wingspan, this.capacity);
  }
}</code></pre>
  </div>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    System.out.println(airplane.move(10));
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
<img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.2.test.png"><br>
</section><br><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    System.out.println(airplane.move(10));
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(<mark>vehicle.move(10)</mark>);
    System.out.println(airplane.move(10));
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md"><mark>Moving</mark>
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    <mark>System.out.println(vehicle.move(10));</mark>
    System.out.println(airplane.move(10));
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
<mark>10.0</mark>
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    System.out.println(<mark>airplane.move(10)</mark>);
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
10.0
<mark>Landing gear up
Moving
Landing gear down</mark>
10.0<br>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    <mark>System.out.println(airplane.move(10));</mark>
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
<mark>10.0</mark><br>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    System.out.println(airplane.move(10));
    <mark>System.out.println(vehicle.describe());</mark>
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0
<mark> </mark>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    System.out.println(airplane.move(10));
    System.out.println(vehicle.describe());
    <mark>System.out.println(airplane.describe());</mark>
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
<mark>I am an airplane with a wingspan of 175.000000 and capacity 53</mark></code></pre>
</section><br>
<section>
  <pre class="" style="font-size: .4em"><code class="java">public class Main{<br>
  public static void main(String[] args){
    Vehicle vehicle = new Vehicle("Boat");
    Airplane airplane = new Airplane("Plane", 175, 53);
    System.out.println(vehicle.move(10));
    System.out.println(airplane.move(10));
    System.out.println(vehicle.describe());
    System.out.println(airplane.describe());
  }
}</code></pre>
  <pre class="" style="font-size: .4em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175.000000 and capacity 53</code></pre>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/13-inherit/12.7.j.mv.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class MotorVehicle extends Vehicle{<br>
  public int number_of_wheels;
  public double engine_volume;<br>
  public MotorVehicle(String name){
    super(name);
    this.number_of_wheels = 2;
    this.engine_volume = 125;
  }<br>
  public String honk_horn(){
    return "";
  }
}</code></pre>
  </div>
</section><br>
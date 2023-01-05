---
type: "reveal"
hidden: true
---
<section>
    <img class="plain stretch" style="" src="/images/13-inherit/12.7.p.uml.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">class Vehicle:<br>
  def __init__(self, name):
    self.__name = name
    self.speed = 1.0<br>
  @property
  def name(self):
    return self.__name<br>
  def move(self, distance):
    print("Moving")
    return distance / self.speed<br>
  def describe(self):
    return ""
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">class Vehicle:<br>
  <mark>def __init__(self, name):
    self.__name = name
    self.speed = 1.0</mark><br>
  @property
  def name(self):
    return self.__name<br>
  def move(self, distance):
    print("Moving")
    return distance / self.speed<br>
  def describe(self):
    return ""</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">class Vehicle:<br>
  def __init__(self, name):
    self.__name = name
    self.speed = 1.0<br>
  @property
  def name(self):
    return self.__name<br>
  <mark>def move(self, distance):
    print("Moving")
    return distance / self.speed</mark><br>
  <mark>def describe(self):
    return ""</mark>
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    self.__name = name
    self.__wingspan = wingspan
    self.__capacity = capacity</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    self.__name = name
    self.__wingspan = wingspan
    self.__capacity = capacity</code></pre><pre class="stretch" style="font-size: .4em"><code class="python">from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    a = Airplane("Test", 123, 45)
    print(a.name)<br>
# main guard
if __name__ == "__main__":
  Main.main()</code></pre>
  </div>
</section><br>
<section>
    <img class="plain stretch" style="" src="/images/13-inherit/12.7.p.2.error.png">
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    <mark style="background-color: red">self.__name = name</mark>
    self.__wingspan = wingspan
    self.__capacity = capacity</code></pre><pre class="stretch" style="font-size: .4em"><code class="python">from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    a = Airplane("Test", 123, 45)
    print(<mark style="background-color: red">a.name</mark>)<br>
# main guard
if __name__ == "__main__":
  Main.main()</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">class Vehicle:<br>
  def __init__(self, name):
    self.__name = name
    self.speed = 1.0<br>
  <mark>@property
  def name(self):
    return self.__name</mark><br>
  def move(self, distance):
    print("Moving")
    return distance / self.speed<br>
  def describe(self):
    return ""
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">class Vehicle:<br>
  def __init__(self, name):
    self.__name = name
    self.speed = 1.0<br>
  @property
  def name(self):
    return <mark style="background-color: red">self.__name</mark><br>
  def move(self, distance):
    print("Moving")
    return distance / self.speed<br>
  def describe(self):
    return ""
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    <mark style="background-color: red">self.__name = name</mark>
    self.__wingspan = wingspan
    self.__capacity = capacity</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    <mark style="background-color: green">super().__init__(name)</mark>
    self.__wingspan = wingspan
    self.__capacity = capacity</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity<br>
  def __landing_gear(self, set):
    if set:
      print("Landing gear down")
    else:
      print("Landing gear up")
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity<br>
  def __landing_gear(self, set):
    if set:
      print("Landing gear down")
    else:
      print("Landing gear up")<br>
  def move(self, distance):
    self.__landing_gear(False)
    print("Moving")
    self.__landing_gear(True)
    return distance / self.speed
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity<br>
  def __landing_gear(self, set):
    if set:
      print("Landing gear down")
    else:
      print("Landing gear up")<br>
  <mark>def move(self, distance):</mark>
    self.__landing_gear(False)
    print("Moving")
    self.__landing_gear(True)
    return distance / self.speed
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity<br>
  def __landing_gear(self, set):
    if set:
      print("Landing gear down")
    else:
      print("Landing gear up")<br>
  def move(self, distance):
    self.__landing_gear(False)
    print("Moving")
    self.__landing_gear(True)
    return distance / self.speed<br>
  <mark>def describe(self):</mark>
    return "I am an airplane with a wingspan of {}
          and capacity {}".format(self.__wingspan,
          self.__capacity)
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.airplane.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from Vehicle import *<br>
class Airplane(Vehicle):<br>
  def __init__(self, name, wingspan, capacity):
    super().__init__(name)
    self.__wingspan = wingspan
    self.__capacity = capacity<br>
  def __landing_gear(self, set):
    if set:
      print("Landing gear down")
    else:
      print("Landing gear up")<br>
  def move(self, distance):
    self.__landing_gear(False)
    print("Moving")
    self.__landing_gear(True)
    return distance / self.speed<br>
  def describe(self):
    return "I am an airplane with a wingspan of {}
          and capacity {}".format(self.__wingspan,
          self.__capacity)
</code></pre>
  </div>
</section><br><br><br><br><br><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(airplane.move(10))
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre>
<img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.2.test.png">
</section><br><br><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(airplane.move(10))
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(<mark>vehicle.move(10)</mark>)
    print(airplane.move(10))
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md"><mark>Moving</mark>
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    <mark>print(vehicle.move(10))</mark>
    print(airplane.move(10))
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
<mark>10.0</mark>
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(<mark>airplane.move(10)</mark>)
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
10.0
<mark>Landing gear up
Moving
Landing gear down</mark>
10.0<br>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    <mark>print(airplane.move(10))</mark>
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
<mark>10.0</mark><br>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(airplane.move(10))
    <mark>print(vehicle.describe())</mark>
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0
<mark> </mark>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(airplane.move(10))
    print(vehicle.describe())
    <mark>print(airplane.describe())</mark><br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
<mark>I am an airplane with a wingspan of 175 and capacity 53</mark></code></pre>
</section><br>
<section>
  <pre class="stretch" style="font-size: .37em"><code class="python">from Vehicle import *
from Airplane import *<br>
class Main:<br>
  @staticmethod
  def main():
    vehicle = Vehicle("Boat")
    airplane = Airplane("Plane", 175, 53)
    print(vehicle.move(10))
    print(airplane.move(10))
    print(vehicle.describe())
    print(airplane.describe())<br>
# main guard
if __name__ == "__main__":
  Main.main()
</code></pre><pre class="" style="font-size: .54em"><code class="md">Moving
10.0
Landing gear up
Moving
Landing gear down
10.0<br>
I am an airplane with a wingspan of 175 and capacity 53</code></pre>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.mv.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Vehicle import *<br>
class MotorVehicle(Vehicle):<br>
  def __init__(self, name):
    super().__init__(name)
    self.number_of_wheels = 2
    self.engine_volume = 125<br>
  def honk_horn():
    return ""</code></pre>
  </div>
</section><br>
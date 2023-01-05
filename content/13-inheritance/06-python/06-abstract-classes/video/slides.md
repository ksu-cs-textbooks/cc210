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
  def __init__(self, name):
    self.__name = name
    <mark>self.speed</mark> = 1.0<br>
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
  def __init__(self, name):
    self.__name = name
    <mark>self._speed = 1.0</mark><br>
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
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0<br>
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
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python"><mark>from abc import ABC, abstractmethod</mark><br>
class Vehicle:<br>
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0<br>
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
    <pre class="stretch" style="font-size: .4em"><code class="python">from abc import ABC, abstractmethod<br>
class Vehicle<mark>(ABC)</mark>:<br>
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0<br>
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
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/13-inherit/12.7.p.vehicle.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="python">from abc import ABC, abstractmethod<br>
class Vehicle(ABC):<br>
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0<br>
  @property
  def name(self):
    return self.__name<br>
  def move(self, distance):
    print("Moving")
    return distance / self.speed<br>
  <mark>@abstractmethod</mark>
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
    <pre class="stretch" style="font-size: .4em"><code class="python">from abc import ABC, abstractmethod<br>
class Vehicle(ABC):<br>
  def __init__(self, name):
    self.__name = name
    self._speed = 1.0<br>
  @property
  def name(self):
    return self.__name<br>
  def move(self, distance):
    print("Moving")
    return distance / self.speed<br>
  @abstractmethod
  def describe(self):
    return ""
</code></pre>
  </div>
</section><br>
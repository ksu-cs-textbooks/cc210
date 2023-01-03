---
type: "reveal"
hidden: true
---

<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:<br>
  def __init__(self, an_y):
    self.y = an_y
    self.x = 5<br>
  def sum(self, a):
    return x + a
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:<br>
  def __init__(self, an_y):
    self.y = an_y
    <mark>self.x = 5</mark><br>
  def sum(self, a):
    return x + a
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  <mark>x = 5</mark><br>
  def __init__(self, an_y):
    self.y = an_y
    <s><mark>self.x = 5</mark></s><br>
  def sum(self, a):
    return x + a
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  def sum(self, a):
    return x + a
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  <mark>@staticmethod</mark>
  def sum(self, a):
    return x + a
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(<mark>self</mark>, a):
    return x + a
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return <mark>Stat.</mark>x + a
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.7.staticuml.stat.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    <mark>some_stat = Stat(7)</mark>
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 5</li>
    <li>some_stat.y = 7</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    <mark>another_stat = Stat(8)</mark><br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 5</li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    <mark>print(some_stat.x)</mark>
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 5</li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    <mark>print(some_stat.x)</mark>
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li><mark>Stat.x = 5</mark></li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    <mark>print(some_stat.y)</mark>
    <mark>print(another_stat.x)</mark>
    <mark>print(another_stat.y)</mark><br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 5</li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    <mark>Stat.x = 25</mark><br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 5</li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    <mark>Stat.x = 25</mark><br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li><mark>Stat.x = 25</mark></li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    <mark>print(some_stat.x)</mark>
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li><mark>Stat.x = 25</mark></li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    <mark>print(another_stat.x)</mark>
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li><mark>Stat.x = 25</mark></li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    <mark>some_stat.x = 10</mark><br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 25</li>
    <li>some_stat.y = 7</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    <mark>some_stat.x = 10</mark><br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 25</li>
    <li>some_stat.y = 7</li>
    <li><mark>some_stat.x = 10</mark></li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    <mark>print(some_stat.x)</mark>
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 25</li>
    <li>some_stat.y = 7</li>
    <li>some_stat.x = 10</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    <mark>print(some_stat.x)</mark>
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 25</li>
    <li>some_stat.y = 7</li>
    <li><mark>some_stat.x = 10</mark></li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    <mark>print(another_stat.x)</mark>
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 25</li>
    <li>some_stat.y = 7</li>
    <li>some_stat.x = 10</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    <mark>print(another_stat.x)</mark>
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li><mark>Stat.x = 25</mark></li>
    <li>some_stat.y = 7</li>
    <li>some_stat.x = 10</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
    <pre class="stretch" style="font-size: .38em"><code class="python">from Stat import *<br>
class Main:<br>
  def main():
    some_stat = Stat(7)
    another_stat = Stat(8)<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    Stat.x = 25<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
    some_stat.x = 10<br>
    print(some_stat.x)
    print(some_stat.y)
    print(another_stat.x)
    print(another_stat.y)<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Stat:
  x = 5<br>
  def __init__(self, an_y):
    self.y = an_y<br>
  @staticmethod
  def sum(a):
    return Stat.x + a
  </code></pre>
  <ul style="font-size: .9em">
    <li>Stat.x = 25</li>
    <li>some_stat.y = 7</li>
    <li>some_stat.x = 10</li>
    <li>another_stat.y = 8</li>
  </ul>
  </div>
</section><br>
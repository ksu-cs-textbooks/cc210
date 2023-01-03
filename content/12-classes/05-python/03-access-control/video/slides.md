---
type: "reveal"
hidden: true
---
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.6.secureuml.secure.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.reset()<br>
  def count(self):
    return len(self.name)<br>
  def reset(self):
    self.name = "test"
    self.secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.6.secureuml.secure.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.reset()<br>
  def count(self):
    return len(self.name)<br>
  def reset(self):
    self.name = "test"
    self.<mark>__</mark>secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.6.secureuml.secure.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.<mark>__</mark>reset()<br>
  def count(self):
    return len(self.name)<br>
  def <mark>__</mark>reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 50%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.6.secureuml.secure.png">
  </div>
  <div style="width: 50%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():<br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    <mark>some_security = Security()</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    <mark>print(some_security.name)</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    <mark>print(some_security.count())</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    <mark>print(some_security.__secret)</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    <mark>print(<mark style="background-color: red">some_security.__secret</mark>)</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    <s>print(some_security.__secret)</s><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    <s>print(some_security.__secret)</s>
    <mark>some_security.__reset()</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    <s>print(some_security.__secret)</s>
    <mark style="background-color: red">some_security.__reset()</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .5em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    <s>print(some_security.__secret)</s>
    <s>some_security.__reset()</s><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    print(<mark>some_security._Security__secret</mark>)
    <mark>some_security._Security__reset()</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 55%">
    <pre class="stretch" style="font-size: .40em"><code class="python">from Security import *<br>
class Main:<br>
  def main():
    some_security = Security()
    print(some_security.name)
    print(some_security.count())
    print(<mark style="background-color: yellow">some_security._Security__secret</mark>)
    <mark style="background-color: yellow">some_security._Security__reset()</mark><br>
if __name__ == "__main__":
    Main.main()
    </code></pre>
  </div>
  <div style="width: 45%">
  <pre class="stretch" style="font-size: .5em"><code class="python">class Security:<br>
  def __init__(self):
    self.__reset()<br>
  def count(self):
    return len(self.name)<br>
  def __reset(self):
    self.name = "test"
    self.__secret = 123
  </code></pre>
  </div>
</section><br>
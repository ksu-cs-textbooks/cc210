---
type: "reveal"
hidden: true
---
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():<br>
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():<br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():
    <mark>Student()</mark><br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():
    <mark>jane =</mark> Student()<br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():
    jane = Student()
    print(<mark>jane.name</mark>)<br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():
    jane = Student()
    print(jane.name)
    <mark>jane.name = "Jane"</mark><br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():
    jane = Student()
    print(jane.name)
    jane.name = "Jane"
    jane.age = jane.age + 15
    jane.student_id = "123" + "456"
    jane.credits = 45
    jane.gpa = jane.gpa - 1.1<br>
    print(jane.name + ": " +
                        jane.student_id)<br>
if __name__ == "__main__":
  Main.main()
</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .5em"><code class="python">from Student import *
from Teacher import *<br>
class Main:<br>
  def main():
    jane = Student()
    print(jane.name)
    jane.name = "Jane"
    jane.age = jane.age + 15
    jane.student_id = "123" + "456"
    jane.credits = 45
    jane.gpa = jane.gpa - 1.1<br>
    print(jane.name + ": " +
                        jane.student_id)<br>
    <mark>jane.birthday()</mark>
    <mark>jane.grade(4, 12)</mark><br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br>
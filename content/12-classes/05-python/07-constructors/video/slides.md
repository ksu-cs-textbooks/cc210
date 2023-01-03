---
type: "reveal"
hidden: true
---
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = "name"
  age = 19
  student_id = "123456987"
  credits = 0
  gpa = 0.0<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = "name"
  age = 19
  student_id = "123456987"
  credits = 0
  gpa = 0.0<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = "name"
  age = 19
  student_id = "123456987"
  credits = 0
  gpa = 0.0<br>
  <mark>def __init__():
    # do nothing
    pass</mark><br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = "name"
  age = 19
  student_id = "123456987"
  credits = 0
  gpa = 0.0<br>
  def __init__(<mark>self</mark>):
    # do nothing
    pass<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = "name"
  age = 19
  student_id = "123456987"
  credits = 0
  gpa = 0.0<br>
  def __init__(self):
    # do nothing
    pass<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = <mark>"name"</mark>
  age = <mark>19</mark>
  student_id = <mark>"123456987"</mark>
  credits = <mark>0</mark>
  gpa = <mark>0.0</mark><br>
  def __init__(self):
    # do nothing
    pass<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  name = "name"
  age = 19
  student_id = "123456987"
  credits = 0
  gpa = 0.0<br>
  def __init__(self):
    <mark>self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0</mark><br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:
  <mark>name = "name"</mark>
  <mark>age = 19</mark>
  <mark>student_id = "123456987"</mark>
  <mark>credits =0</mark>
  <mark>gpa = 0.0</mark><br>
  def __init__(self):
    self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self):
    self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.4.classes.main.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">from Student import *<br>
class Main:<br>
  def main():
    <mark>some_student = Student()</mark>
    print(some_student.name) # "name"
    print(some_student.age)  # 19<br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self):
    self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self<mark>, name, age, student_id,
                                      credits, gpa</mark>):
    self.name = "name"
    self.age = 19
    self.student_id = "123456987"
    self.credits = 0
    self.gpa = 0.0<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self, name, age, student_id,
                                      credits, gpa):
    self.name = <mark>"name"</mark>
    self.age = <mark>19</mark>
    self.student_id = <mark>"123456987"</mark>
    self.credits = <mark>0</mark>
    self.gpa = <mark>0.0</mark><br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self, name<mark>="name"</mark>, age<mark>=19</mark>,
                  student_id<mark>="123456987"</mark>, credits<mark>=0</mark>,
                  gpa<mark>=0.0</mark>):
    self.name = <mark>"name"</mark>
    self.age = <mark>19</mark>
    self.student_id = <mark>"123456987"</mark>
    self.credits = <mark>0</mark>
    self.gpa = <mark>0.0</mark><br>
  # other methods omitted
  </code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self, name="name", age=19,
                  student_id="123456987", credits=0,
                  gpa=0.0):
    self.name = <mark>name</mark>
    self.age = <mark>age</mark>
    self.student_id = <mark>student_id</mark>
    self.credits = <mark>credits</mark>
    self.gpa = <mark>gpa</mark><br>
  # other methods omitted
  </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.6.p.5.constructuml.student.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">class Student:<br>
  def __init__(self, name="name", age=19,
                  student_id="123456987", credits=0,
                  gpa=0.0):
    self.name = name
    self.age = age
    self.student_id = student_id
    self.credits = credits
    self.gpa = gpa<br>
  # other methods omitted
  </code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/images/12-class/11.4.classes.main.png">
  </div>
  <div style="width: 70%">
  <pre class="stretch" style="font-size: .4em"><code class="python">from Student import *<br>
class Main:<br>
  def main():
    some_student = Student()
    print(some_student.name) # "name"
    print(some_student.age)  # 19<br>
    <mark>another_student = Student("John", 25
                          "1239873445", 4, 4.0)</mark>
    print(another_student.name) # "John"
    print(another_student.age)  # 25<br>
if __name__ == "__main__":
  Main.main()
  </code></pre>
  </div>
</section><br>
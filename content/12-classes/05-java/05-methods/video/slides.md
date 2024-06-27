---
type: "reveal"
hidden: true
---<br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){<br>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    <mark>age = age + 1;</mark>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    <mark>this.age = this.age + 1;</mark>
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }<br>
  void grade(int credits, int grade_points){<br>
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }<br>
  void grade(int credits, int grade_points){
    int current_points = this.gpa * this.credits;
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }<br>
  void grade(int credits, int grade_points){
    int current_points = <mark>(int)</mark>this.gpa * this.credits;
  }
}</code></pre>
  </div>
</section><br><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java"><mark>import java.lang.Math;</mark><br>
public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }<br>
  void grade(int credits, int grade_points){
    int current_points = (int)<mark>Math.round</mark>(this.gpa
                                    * this.credits);
  }
}</code></pre>
  </div>
</section><br><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">import java.lang.Math;<br>
public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }<br>
  void grade(int credits, int grade_points){
    int current_points = (int)Math.round(this.gpa
                                    * this.credits);
    this.credits += credits;
    current_points += grade_points;
  }
}</code></pre>
  </div>
</section><br>
<section>
  <div style="float: right; width: 30%">
	   <img class="plain" style="width: 100%" src="/cc210/images/12-class/11.3.methods.student.png">
  </div>
  <div style="width: 70%">
    <pre class="stretch" style="font-size: .4em"><code class="java">import java.lang.Math;<br>
public class Student{
  String name = "name";
  int age = 19;
  String student_id = "123456987";
  int credits = 0;
  double gpa = 0.0;<br>
  void birthday(){
    this.age = this.age + 1;
  }<br>
  void grade(int credits, int grade_points){
    int current_points = (int)Math.round(this.gpa
                                    * this.credits);
    this.credits += credits;
    current_points += grade_points;
    this.gpa = (double)current_points / this.credits;
  }
}</code></pre>
  </div>
</section><br>
---
type: "reveal"
hidden: true
---

<section>
  <p>A program should turn the lights on if the light switch in the room is in the "ON" position. Similarly, it should turn on the lights if it detects there are people in the room using a motion sensor, regardless of whether the light switch is "ON" or "OFF". However, it should respect a master switch, such that if the master switch is off, the lights can not be turned on at all.<p>
</section>
<section>
	<table class="reveal" style="font-size: 0.8em">
		<tr>
			<th>Switch A</th>
			<th>Motion B</th>
			<th>Master C</th>
			<th>Output</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>T</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>F</td>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>T</td>
			<td>F</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>T</td>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
  </table>
</section>
<section>
	<h3>Motion Sensor &#8896; Master</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1a.png">
</section>
<section>
	<h3>Light Switch &#8896; Master</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1b.png">
</section>
<section>
	<h3>Light Switch &#8896; Motion Sensor &#8896; Master</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1c.png">
</section>
<section>
	<h3>Output</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1d.png">
</section>
<section>
	<h3>A &#8896; C</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1e.png">
</section>
<section>
	<h3>B &#8896; C</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1f.png">
</section>
<section>
	<h3>(A &#8896; C) ? (B &#8896; C)</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1g.png">
</section>
<section>
	<h3>(A &#8896; C) &#8897; (B &#8896; C)</h3>
	<img class="stretch plain" src="/cc210/images/03-bool/3.4.1g.png">
</section>
<section>
	<h4>(Light Switch &#8896; Master Switch)<br>&#8897;<br>(Motion Sensor &#8896; Master Switch)</h4>
</section>
<section>
	<table class="reveal" style="font-size: 0.8em">
		<tr>
			<th>Switch A</th>
			<th>Motion B</th>
			<th>Master C</th>
			<th>Output</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>T</td>
			<td>F</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>F</td>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>T</td>
			<td>F</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>F</td>
			<td>F</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>T</td>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
  </table>
</section>
<section>
	<table class="reveal" style="font-size: 0.8em">
		<tr>
			<th>Switch A</th>
			<th>Motion B</th>
			<th>Master C</th>
			<th>Output</th>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>F</td>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>T</td>
			<td>F</td>
			<td>T</td>
			<td>T</td>
		</tr>
		<tr style="font-weight: bold; color: #512888">
			<td>T</td>
			<td>T</td>
			<td>T</td>
			<td>T</td>
		</tr>
  </table>
	<p style="font-size: 1.5em">(&not;A &#8896; B &#8896; C)<br>&#8897; (A &#8896; &not;B &#8896; C)<br>&#8897; (A &#8896; B &#8896; C)</p>
</section>
<section>
  <p style="font-size: 1.5em">(&not;A &#8896; B &#8896; C)<br>&#8897; (A &#8896; &not;B &#8896; C)<br>&#8897; (A &#8896; B &#8896; C)</p>
</section>
<section>
  <p style="font-size: 1.5em">(&not;A &#8896; B &#8896; C)<br>&#8897; (A &#8896; &not;B &#8896; C)<br>&#8897; (A &#8896; B &#8896; C)<br><mark>&#8897; (A &#8896; B &#8896; C)</mark></p>
</section>
<section>
  <p style="font-size: 1.5em">(&not;A &#8896; B &#8896; C)<br><mark>&#8897; (A &#8896; B &#8896; C)</mark><br>&#8897; (A &#8896; &not;B &#8896; C)<br>&#8897; (A &#8896; B &#8896; C)</p>
</section>
<section>
  <p style="font-size: 1.5em">(&not;A &#8896; B &#8896; C)<br>&#8897; (A &#8896; B &#8896; C)<br>&#8897; (<mark>&not;B &#8896; A</mark> &#8896; C)<br>&#8897; (<mark>B &#8896; A</mark> &#8896; C)</p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><span style="font-size: 1.7em">(</span><span style="font-size: 1.3em">(</span>&not;A &#8896; (B &#8896; C)<span style="font-size: 1.3em">)</span><br>&#8897; <span style="font-size: 1.3em">(</span>A &#8896; (B &#8896; C)<span style="font-size: 1.3em">)</span><span style="font-size: 1.7em">)</span><br>&#8897;<br><span style="font-size: 1.7em">(</span><span style="font-size: 1.3em">(</span>&not;B &#8896; (A &#8896; C)<span style="font-size: 1.3em">)</span><br>&#8897; <span style="font-size: 1.3em">(</span>B &#8896; (A &#8896; C)<span style="font-size: 1.3em">)</span><span style="font-size: 1.7em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><span style="font-size: 1.7em">(</span><span style="font-size: 1.3em">(</span>&not;A &#8896; <mark>(B &#8896; C)</mark><span style="font-size: 1.3em">)</span><br>&#8897; <span style="font-size: 1.3em">(</span>A &#8896; <mark>(B &#8896; C)</mark><span style="font-size: 1.3em">)</span><span style="font-size: 1.7em">)</span><br>&#8897;<br><span style="font-size: 1.7em">(</span><span style="font-size: 1.3em">(</span>&not;B &#8896; (A &#8896; C)<span style="font-size: 1.3em">)</span><br>&#8897; <span style="font-size: 1.3em">(</span>B &#8896; (A &#8896; C)<span style="font-size: 1.3em">)</span><span style="font-size: 1.7em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><mark><span style="font-size: 1.3em">(</span>(B &#8896; C) &#8896; (&not;A &#8897; A)<span style="font-size: 1.3em">)</span></mark><br>&#8897;<br><span style="font-size: 1.7em">(</span><span style="font-size: 1.3em">(</span>&not;B &#8896; (A &#8896; C)<span style="font-size: 1.3em">)</span><br>&#8897; <span style="font-size: 1.3em">(</span>B &#8896; (A &#8896; C)<span style="font-size: 1.3em">)</span><span style="font-size: 1.7em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><mark><span style="font-size: 1.3em">(</span>(B &#8896; C) &#8896; (&not;A &#8897; A)<span style="font-size: 1.3em">)</span></mark><br>&#8897;<br><span style="font-size: 1.7em">(</span><span style="font-size: 1.3em">(</span>&not;B &#8896; <mark>(A &#8896; C)</mark><span style="font-size: 1.3em">)</span><br>&#8897; <span style="font-size: 1.3em">(</span>B &#8896; <mark>(A &#8896; C)</mark><span style="font-size: 1.3em">)</span><span style="font-size: 1.7em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><span style="font-size: 1.3em">(</span>(B &#8896; C) &#8896; (&not;A &#8897; A)<span style="font-size: 1.3em">)</span><br>&#8897;<br><mark><span style="font-size: 1.3em">(</span>(A &#8896; C) &#8896; (&not;B &#8897; B)<span style="font-size: 1.3em">)</span></mark></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><span style="font-size: 1.3em">(</span>(B &#8896; C) &#8896; <mark>(&not;A &#8897; A)</mark><span style="font-size: 1.3em">)</span><br>&#8897;<br><span style="font-size: 1.3em">(</span>(A &#8896; C) &#8896; <mark>(&not;B &#8897; B)</mark><span style="font-size: 1.3em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><span style="font-size: 1.3em">(</span>(B &#8896; C) &#8896; <mark>T</mark><span style="font-size: 1.3em">)</span><br>&#8897;<br><span style="font-size: 1.3em">(</span>(A &#8896; C) &#8896; <mark>T</mark><span style="font-size: 1.3em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em"><span style="font-size: 1.3em">(</span>(B &#8896; C) <mark>&#8896; T</mark><span style="font-size: 1.3em">)</span><br>&#8897;<br><span style="font-size: 1.3em">(</span>(A &#8896; C) <mark>&#8896; T</mark><span style="font-size: 1.3em">)</span></p>
</section>
<section>
  <p style="font-size: 1.5em; line-height: 1.55em">(B &#8896; C)<br>&#8897;<br>(A &#8896; C)</p>
</section>
<section>
	<h4>(Motion Sensor &#8896; Master Switch)<br>&#8897;<br>(Light Switch &#8896; Master Switch)</h4>
</section>
<section>
	<h4>(Master Switch)<br>&#8896;<br>(Light Switch &#8897; Motion Sensor)</h4>
</section>

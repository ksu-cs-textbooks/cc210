---
type: "reveal"
hidden: true
---

<section>
	<img class="stretch plain" src="/cc210/images/03-bool/3.3.demorgan.wikimedia.jpg">
	<p class="imagecredit">Image Credit: <a href="https://en.wikipedia.org/wiki/Augustus_De_Morgan">Wikimedia</a></p>
</section>
<section>
<section>
	<h1>&not;(A &#8896; B)</h1>
</section>
<section>
	<table class="reveal">
		<tr>
			<th>A</th>
			<th>B</th>
			<th>A &#8896; B</th>
			<th>&not;(A &#8896; B)</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
			<td></td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>F</td>
			<td></td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>F</td>
			<td></td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>T</td>
			<td></td>
		</tr>
	</table>
</section>
<section>
	<table class="reveal">
		<tr>
			<th>A</th>
			<th>B</th>
			<th>A &#8896; B</th>
			<th>&not;(A &#8896; B)</th>
		</tr>
		<tr>
			<td>F</td>
			<td>F</td>
			<td>F</td>
			<td>T</td>
		</tr>
		<tr>
			<td>F</td>
			<td>T</td>
			<td>F</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>F</td>
			<td>F</td>
			<td>T</td>
		</tr>
		<tr>
			<td>T</td>
			<td>T</td>
			<td>T</td>
			<td>F</td>
		</tr>
	</table>
</section>
<section>
	<h1>&not;(A &#8896; B)</h1>
	<h1>&not;A &#8897; &not;B</h1>
</section>
<section>
	<h1>&not;(A &#8897; B)</h1>
	<h1>&not;A &#8896; &not;B</h1>
</section>
<section>
	<h3>De Morgan's Laws</h3>
  <ol>
		<li>Distribute &not; Inside</li>
		<li>Invert Signs (&#8897; and &#8896;)</li>
	</ol>
</section>

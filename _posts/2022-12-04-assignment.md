---
keywords: fastai
description: Hacks
title: Unit 3 Sections 5-7 Hacks
toc: true
badges: true
comments: true
categories: [Student Teaching]
nb_path: _notebooks/2022-12-04-assignment.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-12-04-assignment.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>For hacks, <mark>make a copy of this notebook and answer the questions or complete the code</mark>, as described in comments. Additionally, <mark>blog about any missed questions</mark>, or what you learned from this lesson.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="3.5-Hacks">3.5 Hacks<a class="anchor-link" href="#3.5-Hacks"> </a></h1><h2 id="Binary-Practice">Binary Practice<a class="anchor-link" href="#Binary-Practice"> </a></h2><p>Using psuedocode operators determine if the statements are true or false. The number type will be indicated in parentheses.</p>
<p><strong>1. 90(D) = 1000(B)</strong></p>
<ul>
<li>A. True</li>
<li>B. False (answer)</li>
</ul>
<p><strong>2. 10(D) ≠ 0110(B)</strong></p>
<ul>
<li>A. True (answer)</li>
<li>B. False</li>
</ul>
<p><strong>3. 56(D) ≥ 111000(B)</strong></p>
<ul>
<li>A. True (answer)</li>
<li>B. False</li>
</ul>
<p><strong>3. 99(D) &lt; 1110011(B)</strong></p>
<ul>
<li>A. True (answer)</li>
<li>B. False</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Now, complete the binary truth tables</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<html>
<style>
    table, th, td { 
        border:2px solid white;
    }
</style>
    <div>AND Operator</div>
    <div>
        <table>
            <tr>
                <th>Value 1</th>
                <th>Value 2</th>
                <th>Result</th>
            </tr>
            <tr>
                <td>1</td>
                <td>1</td>
                <td>1</td>
            </tr>
            <tr>
                <td>1</td>
                <td>0</td>
                <td>0</td>
            </tr>
            <tr>
                <td>0</td>
                <td>1</td>
                <td>0</td>
            </tr>
            <tr>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
        </table>
    </div>
    <div>OR Operator</div>
    <div>
        <table>
            <tr>
                <th>Value 1</th>
                <th>Value 2</th>
                <th>Result</th>
            </tr>
            <tr>
                <td>1</td>
                <td>1</td>
                <td>1</td>
            </tr>
            <tr>
                <td>1</td>
                <td>0</td>
                <td>1</td>
            </tr>
            <tr>
                <td>0</td>
                <td>1</td>
                <td>1</td>
            </tr>
            <tr>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
        </table>
    </div>
    <div>Not operator</div>
    <div>
        <table>
            <tr>
                <th>Not</th>
                <th>Value</th>
                <th>Result</th>
            </tr>
            <tr>
                <td>Not</td>
                <td>1</td>
                <td>0</td>
            </tr>
            <tr>
                <td>Not</td>
                <td>0</td>
                <td>1</td>
            </tr>
        </table>
    </div>
</html>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Python-Practice">Python Practice<a class="anchor-link" href="#Python-Practice"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Practice with these statements</span>

<span class="nb">print</span><span class="p">(</span><span class="mi">20</span> <span class="o">==</span> <span class="mi">30</span><span class="p">)</span> <span class="c1"># How can you change the operator to print a value of False? </span>
<span class="c1"># Answer: by changing it to the equal sign because 20 does not equal 30, so it would return as false</span>

<span class="n">x</span> <span class="o">=</span> <span class="mi">30</span>
<span class="n">y</span> <span class="o">=</span> <span class="mi">20</span>
<span class="n">z</span> <span class="o">=</span> <span class="mi">10</span>
<span class="nb">print</span><span class="p">(</span><span class="n">x</span> <span class="o">&gt;=</span> <span class="n">y</span> <span class="o">+</span> <span class="n">z</span><span class="p">)</span> <span class="c1"># How can this return true by only manipulating the operator?</span>
<span class="c1"># by changing it to a greater than or equal to sign, that way 30 is equal to 30, so it will return as true </span>

<span class="c1"># Manipulate the variables x, y, and z to make the below statement return true</span>
<span class="c1"># I added y to z so that 30 == 30, so it would return as true </span>
<span class="nb">print</span><span class="p">(</span><span class="n">x</span> <span class="o">==</span> <span class="n">z</span> <span class="o">+</span> <span class="n">y</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>False
True
True
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="3.6-Hacks">3.6 Hacks<a class="anchor-link" href="#3.6-Hacks"> </a></h1><h2 id="AP-Prep">AP Prep<a class="anchor-link" href="#AP-Prep"> </a></h2><p><strong>1. What is displayed by this code?</strong></p>
<ul>
<li>result &lt;-- 75</li>
<li>IF result &lt; 80 {
  DISPLAY("Please schedule a retake.")
}</li>
<li>ELSE {
  DISPLAY("Nice job!")
}</li>
</ul>
<ol>
<li>Nice job!</li>
<li>Display</li>
<li>Please schedule a retake. (answer)</li>
<li>75</li>
</ol>
<p><strong>2. How is an if statement different from an if-else statement.</strong></p>
<ol>
<li>Extra words.</li>
<li>An if statement will only go through a process if a condition is met. An if-else statement will go through code no matter the conditions. (answer)</li>
<li>They are the exact same.</li>
<li>An if statement will go through the entire code segment every single time and the if-else statement is always used in an algorithm, no matter the conditions.</li>
</ol>
<p><strong>3. What would be most appropriate for this situation? Ben wants to check his bank account. If his car fuel is full, he will go to the bank. Otherwise, he will go home. If he goes to the bank, he will withdraw money only if his balance is above $1000.</strong></p>
<ol>
<li>If statement</li>
<li>If-else statement (answer)</li>
</ol>
<p><strong>4. What would be most appropriate for this situation? Luke wants to play basketball. If it is sunny outside he will go to the park to play basketball.</strong></p>
<ol>
<li>If statement (answer)</li>
<li>If-else statement</li>
</ol>
<h2 id="Using-Python">Using Python<a class="anchor-link" href="#Using-Python"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">animals</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;lion&quot;</span><span class="p">,</span> <span class="s2">&quot;tiger&quot;</span><span class="p">,</span> <span class="s2">&quot;wildebeest&quot;</span><span class="p">,</span> <span class="s2">&quot;shark&quot;</span><span class="p">,</span> <span class="s2">&quot;jellyfish&quot;</span><span class="p">,</span> <span class="s2">&quot;blobfish&quot;</span><span class="p">,</span> <span class="s2">&quot;raven&quot;</span><span class="p">]</span>
 
<span class="nb">print</span><span class="p">(</span><span class="n">animals</span><span class="p">)</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">animals</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">i</span> <span class="o">==</span> <span class="s2">&quot;shark&quot;</span><span class="p">:</span> <span class="c1"># What boolean value does this statement cause? Answer: True</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Fun Fact: The smallest shark is the dwarf lantern shark, and it is small enough to hold in your hand!&quot;</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>

<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">animals</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">i</span> <span class="o">==</span> <span class="s2">&quot;raven&quot;</span><span class="p">:</span> <span class="c1"># if the item in the list animals is raven </span>
        <span class="nb">print</span><span class="p">(</span><span class="n">i</span> <span class="o">+</span> <span class="s2">&quot;s live in the desert&quot;</span><span class="p">)</span> <span class="c1">#print </span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">i</span> <span class="o">+</span> <span class="s2">&quot;(e)s do not live in the desert&quot;</span><span class="p">)</span> <span class="c1"># if the item in the list animals is not raven, print this line </span>
        
        
 
<span class="c1"># Practice</span>
<span class="c1"># Using only one more if statement, alter the code to print out a statement saying if an animal lives in the desert, based on booleans</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>[&#39;lion&#39;, &#39;tiger&#39;, &#39;wildebeest&#39;, &#39;shark&#39;, &#39;jellyfish&#39;, &#39;blobfish&#39;, &#39;raven&#39;]
lion
tiger
wildebeest
Fun Fact: The smallest shark is the dwarf lantern shark, and it is small enough to hold in your hand!
jellyfish
blobfish
raven
lion(e)s do not live in the desert
tiger(e)s do not live in the desert
wildebeest(e)s do not live in the desert
shark(e)s do not live in the desert
jellyfish(e)s do not live in the desert
blobfish(e)s do not live in the desert
ravens live in the desert
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="3.7-Hacks">3.7 Hacks<a class="anchor-link" href="#3.7-Hacks"> </a></h1><h2 id="Exercise-1">Exercise 1<a class="anchor-link" href="#Exercise-1"> </a></h2><ul>
<li>Create dictionaries for multiple food items, with the listed specifications<ul>
<li>Chicken Alfredo, Meat: Chicken, Time to Prepare: 60 minutes</li>
<li>Cheese Quesadilla, Meat: None, Time to Prepare: 10 minutes</li>
<li>Beef Wellington, Meat: Beef, Time to Prepare: 150 minutes</li>
</ul>
</li>
<li>Used nested conditionals, determine which meal you can cook, given that a) you have no meat at home, and b) you only have 30 minutes to make the meal</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#dictionaries defined below with all of the specifications</span>
<span class="n">chickenAlfredo</span> <span class="o">=</span>  <span class="p">{</span>
        <span class="s2">&quot;isMeat&quot;</span><span class="p">:</span> <span class="kc">True</span><span class="p">,</span>
        <span class="s2">&quot;prepTime&quot;</span><span class="p">:</span> <span class="mi">60</span><span class="p">}</span>

<span class="n">cheeseQuesadilla</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;isMeat&quot;</span><span class="p">:</span> <span class="kc">False</span><span class="p">,</span>
            <span class="s2">&quot;prepTime&quot;</span><span class="p">:</span> <span class="mi">10</span><span class="p">}</span>

<span class="n">beefWellington</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;isMeat&quot;</span><span class="p">:</span> <span class="kc">True</span><span class="p">,</span>
            <span class="s2">&quot;prepTime&quot;</span><span class="p">:</span> <span class="mi">150</span><span class="p">}</span> 

<span class="k">def</span> <span class="nf">cook</span><span class="p">(</span><span class="n">meal</span><span class="p">):</span> <span class="c1">#define a function cook(meal)</span>
    <span class="k">if</span> <span class="n">meal</span><span class="p">[</span><span class="s2">&quot;isMeat&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="kc">False</span><span class="p">:</span> <span class="c1"># if isMeat in my dictionary is false, then proceeds to nested iteration</span>
        <span class="k">if</span> <span class="n">meal</span><span class="p">[</span><span class="s2">&quot;prepTime&quot;</span><span class="p">]</span> <span class="o">&lt;=</span> <span class="mi">30</span><span class="p">:</span> <span class="c1">#if meal &quot;prepTime&quot; from my dictionary is less than or equal to 30 </span>
            <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Yes, you can make this meal with what you have in the fridge!&quot;</span><span class="p">)</span> <span class="c1">#print this statement</span>
        <span class="k">else</span><span class="p">:</span> 
            <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;No, you can&#39;t make this meal, you don&#39;t have enough time.&quot;</span><span class="p">)</span> 
<span class="c1">#this line wont print because beef wellington and chicken parm both have meat == true, so it won&#39;t get to the next statement and will print the else statement below</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;No, you can&#39;t make this meal, you don&#39;t have meat.&quot;</span><span class="p">)</span>
        <span class="c1"># if meat is true, this line will print </span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;can I make chicken alfredo?&quot;</span><span class="p">)</span>     
<span class="n">cook</span><span class="p">(</span><span class="n">chickenAlfredo</span><span class="p">)</span> <span class="c1"># function will print based on defined dictionaries </span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;can I make a cheese quesadilla?&quot;</span><span class="p">)</span>
<span class="n">cook</span><span class="p">(</span><span class="n">cheeseQuesadilla</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;can I make beef wellington?&quot;</span><span class="p">)</span>
<span class="n">cook</span><span class="p">(</span><span class="n">beefWellington</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>can I make chicken alfredo?
No, you can&#39;t make this meal.
can I make a cheese quesadilla?
Yes, you can make this meal with what you have in the fridge!
can I make beef wellington?
No, you can&#39;t make this meal.
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Exercise-2">Exercise 2<a class="anchor-link" href="#Exercise-2"> </a></h2><p><img src="https://github.com/kayleehou/myproject/blob/master/images/hacksflowchart.PNG?raw=true" alt=""></p>
<ul>
<li>Mr. Yeung would like to grade live reviews.   </li>
<li>He wants to see if each student has at least 2 issues on their project. If they don't they receive a score of 2.0.</li>
<li>If they have at least 2 issues, check that they have completed at least 5 of their scrumboard tasks.</li>
<li>If they have completed 5 scrumboard tasks, give the student a 2.7. If they have not completed 5 scrumboard tasks, give them a score of 2.5. If they have completed more than 5 tasks, give them a score of 3.0.</li>
<li>How much would a student with 3 issues and 1 complete scrumboard task receive?</li>
</ul>
<p><strong>ANSWER:</strong> they would receive a 2.0 because they 3 issues which is more than 2, however, they wouldn't be able to get any more points because they don't have at least 5 scrumboard tasks</p>

</div>
</div>
</div>
</div>
 


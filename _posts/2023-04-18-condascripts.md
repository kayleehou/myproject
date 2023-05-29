---
keywords: fastai
title: Conda Scripts Lesson
toc: true
categories: [Student Teaching]
nb_path: _notebooks/2023-04-18-condascripts.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2023-04-18-condascripts.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="For-Windows">For Windows<a class="anchor-link" href="#For-Windows"> </a></h1><p><img src="https://github.com/kayleehou/myproject/blob/master/images/condadiagram.PNG?raw=true" alt="conda image"></p>
<p>After you've installed VSCode using WSL, install Anaconda on WSL.</p>
<p>Anaconda is like a big tool box for your computer, it has tools and libraries that you might need for data analysis, programming, and computing. Conda is a tool that helps you manage these tools inside Anaconda. It lets you install, update, delete, and organize packages and materials. Anaconda Python packages include pandas, numpy, sqlite, jupyter, bash, and other kernels. Conda script tells Conda what tools and materials you need and how to install them in your Anaconda toolbox.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Type these commands in powershell or terminal</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">PS</span> <span class="n">C</span><span class="p">:</span>\<span class="n">Users</span>\<span class="n">UserName</span><span class="o">&gt;</span> <span class="n">wsl</span>  <span class="c1"># Windows prompt to WSL command</span>
<span class="err">$</span> <span class="n">cd</span> <span class="o">/</span><span class="n">tmp</span> <span class="c1"># used to store temporary files </span>
<span class="err">$</span> <span class="n">wget</span> <span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">repo</span><span class="o">.</span><span class="n">anaconda</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">archive</span><span class="o">/</span><span class="n">Anaconda3</span><span class="o">-</span><span class="mf">2023.03</span><span class="o">-</span><span class="n">Linux</span><span class="o">-</span><span class="n">x86_64</span><span class="o">.</span><span class="n">sh</span> <span class="c1"># downloadable file</span>
<span class="err">$</span> <span class="n">chmod</span> <span class="o">+</span><span class="n">x</span> <span class="n">Anaconda3</span><span class="o">-</span><span class="mf">2022.05</span><span class="o">-</span><span class="n">Linux</span><span class="o">-</span><span class="n">x86_64</span><span class="o">.</span><span class="n">sh</span> <span class="c1"># chmod (change mode command) changes permissions for a file or directory </span>
<span class="c1"># Answer yes to all the prompts</span>
<span class="err">$</span> <span class="o">./</span><span class="n">Anaconda3</span><span class="o">-</span><span class="mf">2022.05</span><span class="o">-</span><span class="n">Linux</span><span class="o">-</span><span class="n">x86_64</span><span class="o">.</span><span class="n">sh</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Start a new WSL Command or Powershell. Now the WSL prompt should be prefixed with (base) from Anaconda install. If not, go back to Anaconda install. The base prefix indicates that you are running inside the conda/anaconda environment. The command "conda deactivate" should bring you back.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">PS</span> <span class="n">C</span><span class="p">:</span>\<span class="n">Users</span>\<span class="n">ShayM</span><span class="o">&gt;</span> <span class="n">wsl</span>  <span class="c1"># Windows prompt</span>
<span class="p">(</span><span class="n">base</span><span class="p">)</span> <span class="n">shay</span><span class="nd">@MSI</span><span class="p">:</span><span class="o">/</span><span class="n">mnt</span><span class="o">/</span><span class="n">c</span><span class="o">/</span><span class="n">Users</span><span class="o">/</span><span class="n">ShayM</span><span class="err">$</span> <span class="n">cd</span> <span class="o">~</span> <span class="c1"># WSL prompt</span>
<span class="p">(</span><span class="n">base</span><span class="p">)</span> <span class="n">shay</span><span class="nd">@MSI</span><span class="p">:</span><span class="o">~</span><span class="err">$</span> <span class="c1"># WSL home, best place to install files</span>

<span class="c1"># you can check your conda versions</span>
<span class="p">(</span><span class="n">base</span><span class="p">)</span> <span class="nb">id</span><span class="p">:</span><span class="o">~</span><span class="err">$</span> <span class="n">conda</span> <span class="o">--</span><span class="n">version</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="https://github.com/kayleehou/myproject/blob/master/images/condaimage2.PNG?raw=true" alt="command prompt view"></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="For-MacOS">For MacOS<a class="anchor-link" href="#For-MacOS"> </a></h1><blockquote><p>Python2 install on MacOS</p>
<ul>
<li>Install <a href="https://www.python.org/ftp/python/2.7.18/python-2.7.18-macosx10.9.pkg">Python2</a>&gt; VSCode install on MacOS.  </li>
<li>Install <a href="https://code.visualstudio.com/docs/setup/mac">VSCode</a>&gt; Anaconda install on MacOS.</li>
<li>Download for MacOS:<a href="https://www.anaconda.com/products/distribution">Anaconda</a>- Run Install: Answer yes to questions
Homebrew install on MacOS</li>
<li>Homebrew is a tool that helps you easily install and manage software on your Mac. Think of it like a virtual store for your computer where you can browse, download and install a variety of useful programs and tools.</li>
<li>Copy and Paste to Install from Terminal <a href="https://brew.sh">Homebrew</a>    - Copy <code>bash ... curl ...</code>  command using copy box on website<ul>
<li>Launch <code>terminal</code> from search bar</li>
<li>Paste <code>bash ... curl ...</code> command into Terminal ... </li>
<li>Make sure command starts, this should provide feedback/output in terminal and could take a long time, like 10-min, there could be a prompt in the middle, at about 5-minutes.  Follow any on screen instructions provided in terminal output to finish.</li>
</ul>
</li>
<li>Homebrew installs a tool called "brew" which helps add and manage developer packages on MacOS. </li>
</ul>
</blockquote>
<p>Start a new WSL terminal. Now the terminal prompt should be prefixed with (base) from Anaconda install. If not, go back to Anaconda install.</p>
<blockquote><p>Having Homebrew and Anaconda allows you to easily install Key Packages needed on MacOS like the commands below are all neccessary:```bash$ brew list # list packages
$ brew update # update package list
$ brew upgrade # upgrade packages
$ brew install git  # install latest git
$ brew install python # install python3 for development
$ python --version # version of python3 installed
$ brew install java # openjdk install</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Hacks">Hacks<a class="anchor-link" href="#Hacks"> </a></h1><ul>
<li>Screen shot that you have conda installed </li>
<li>Make your own comparison for how Anaconda, conda, and conda scripts relate like my toolbox comparison. Add pictures!  </li>
</ul>

</div>
</div>
</div>
</div>
 

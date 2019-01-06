---
layout: page
title: Project 0 (Unix/Python/Autograder Tutorial)
permalink: /projects/project0/
---

<div class="home">

<div class="project">
<link rel="shortcut icon" href="../../_images/bots-and-robots.ico" type="image/x-icon">
<link rel="stylesheet" href="../../css/bootstrap.min.css">
<link rel="stylesheet" href="../../css/style.css" type="text/css" media="all">

<b>Acknowledgements</b>: The Pacman AI projects were developed at UC Berkeley. The core projects and autograders were primarily created by John DeNero and Dan Klein. Student side autograding was added by Brad Miller, Nick Hay, and Pieter Abbeel. We thank them for their permission to use it as a part of this course.


<hr>
<h2>Table of Contents</h2>
<ul>
<li><a href="#Introduction">Introduction</a></li>
<li><a href="#UNIXBasics">UNIX Basics</a></li>
<li><a href="#Installation">Python Installation</a></li>
<li><a href="#PythonBasics">Python Basics</a></li>
<li><a href="#Autograding">Autograding</a></li>
<li><a href="#Q1">Q1: Addition</a></li>
<li><a href="#Q2">Q2: BuyLotsOfFruit</a></li>
<li><a href="#Q3">Q3: ShopSmart</a></li>
<li><a href="#Submission">Submission</a></li>
</ul>
</div>

<hr>

<div class="project">
<h2><a name="Introduction"></a>Introduction</h2>
<p>The projects for this class assume you use Python 3.6. </p>
<p>Project 0 will cover the following:</p>
<ul>
<li>A mini-UNIX tutorial (particularly important if you work on instructional machines),</li>
<li>Instructions on how to set up the right Python version,</li>
<li>A mini-Python tutorial,</li>
<li>Project grading: <!--all projects in this course will be autograded after you submit your code through the edX website. For all projects you can submit as many times as you like until the deadline.--> Every project's release includes its autograder for you to run yourself. <!--This is the recommended, and fastest, way to test your code, but keep in mind you need to submit into the edX system to get your grade registered.--></li>
</ul>
<p><strong>Files to Edit and Submit:</strong> You will fill in portions of <code>addition.py</code>, <code>buyLotsOfFruit.py</code>, and <code>shopSmart.py</code> in <code><a href="./tutorial.zip">tutorial.zip</a></code> during the assignment. You should submit these files with your code and comments. Please <em>do not</em> change the other files in this distribution or submit any of our original files other than these files.</p>
<p><strong>Evaluation:</strong> Your code will be autograded for technical correctness. Please <em>do not</em> change the names of any provided functions or classes within the code, or you will wreak havoc on the autograder. However, the correctness of your implementation -- not the autograder's judgements -- will be the final judge of your score. If necessary, we will review and grade assignments individually to ensure that you receive due credit for your work.</p>
<p><strong>Academic Dishonesty:</strong> We will be checking your code against other submissions in the class for logical redundancy. If you copy someone else's code and submit it with minor changes, we will know. These cheat detectors are quite hard to fool, so please don't try. We trust you all to submit your own work only; <em>please</em> don't let us down. If you do, we will pursue the strongest consequences available to us.</p>
<p><strong>Getting Help:</strong> You are not alone! If you find yourself stuck on something, contact the course staff for help. Office hours, section, and the discussion forum are there for your support; please use them. If you can't make our office hours, let us know and we will schedule more. We want these projects to be rewarding and instructional, not frustrating and demoralizing. But, we don't know when or how to help unless you ask.</p>
<p><strong>Discussion:</strong> Please be careful not to post spoilers.</p>
<p><strong>Due:</strong> <b>Monday 1/21</b> at <b>11:59 pm</b> </p>

</div>

<hr>

<div class="project">
<h2><a name="UNIXBasics"></a>Unix Basics</h2>
<p>Here are basic commands to navigate UNIX and edit files.</p>
<h4>File/Directory Manipulation</h4>
<p>When you open a terminal window, you're placed at a command prompt:</p>
<div class="code_snippet">
<p><code> [cs188-ta@nova ~]$ </code></p>
</div>
<p>The prompt shows your username, the host you are logged onto, and your current location in the directory structure (your path). The tilde character is shorthand for your home directory. Note your prompt may look slightly different. To make a directory, use the <code>mkdir</code> command. Use <code>cd</code> to change to that directory:</p>
<div class="code_snippet">
<p><code> [cs188-ta@nova ~]$ mkdir foo<br> [cs188-ta@nova ~]$ cd foo<br> [cs188-ta@nova ~/foo]$ </code></p>
</div>
<p>Use <code>ls</code> to see a listing of the contents of a directory, and <code>touch</code> to create an empty file:</p>
<div class="code_snippet">
<p><code> [cs188-ta@nova ~/foo]$ ls<br> [cs188-ta@nova ~/foo]$ touch hello_world<br> [cs188-ta@nova ~/foo]$ ls<br> hello_world<br> [cs188-ta@nova ~/foo]$ cd ..<br> [cs188-ta@nova ~]$ <br> </code></p>
</div>
<p>Download <a href="./python_basics.zip">python_basics.zip</a> into your home directory (note: the zip file's name may be slightly different when you download it). Use <code>unzip</code> to extract the contents of the zip file:</p>
<div class="code_snippet">
    <p><code> [cs188-ta@nova ~]$ ls *.zip<br> python_basics.zip<br> [cs188-ta@nova ~]$ unzip python_basics.zip<br> [cs188-ta@nova ~]$ cd python_basics<br> [cs188-ta@nova ~/python_basics]$ ls<br> foreach.py<br> helloWorld.py<br> listcomp.py<br> listcomp2.py<br> quickSort.py<br> shop.py<br> shopTest.py<br> </code></p>
</div>
<p>Some other useful Unix commands:</p>
<ul>
<li><code>cp</code> copies a file or files</li>
<li><code>rm</code> removes (deletes) a file</li>
<li><code>mv</code> moves a file (i.e., cut/paste instead of copy/paste)</li>
<li><code>man</code> displays documentation for a command</li>
<li><code>pwd</code> prints your current path</li>
<li><code>xterm</code> opens a new terminal window</li>
<li><code>firefox</code> opens a web browser</li>
<li>Press "Ctrl-c" to kill a running process</li>
<li>Append <code>&amp;</code> to a command to run it in the background</li>
<li><code>fg</code> brings a program running in the background to the foreground</li>
</ul>
<h4>The Emacs text editor</h4>
<p>Emacs is a customizable text editor which has some nice features specifically tailored for programmers. However, you can use any other text editor that you may prefer (such as <code>vi</code>, <code>pico</code>, or <code>joe</code> on Unix; or Notepad on Windows; or TextWrangler on OS X; and <a href="http://en.wikipedia.org/wiki/Python_IDE#Python">many more</a>).</p>
<p>To run Emacs, type <code>emacs</code> at a command prompt:</p>
<div class="code_snippet">
<p><code> [cs188-ta@nova ~/python_basics]$ emacs helloWorld.py &amp;<br> [1] 3262 </code></p>
</div>
<p>Here we gave the argument <code>helloWorld.py</code> which will either open that file for editing if it exists, or create it otherwise. Emacs notices that this is a Python source file (because of the <code>.py</code> ending) and enters Python-mode, which is supposed to help you write code. When editing this file you may notice some of that text becomes automatically colored: this is syntax highlighting to help you distinguish items such as keywords, variables, strings, and comments. Pressing Enter, Tab, or Backspace may cause the cursor to jump to weird locations: this is because Python is very picky about indentation, and Emacs is predicting the proper tabbing that you should use.</p>
<p>Some basic Emacs editing commands (<code>C-</code> means "while holding the Ctrl-key"):</p>
<ul>
<li><code>C-x C-s</code> Save the current file</li>
<li><code>C-x C-f</code> Open a file, or create a new file it if doesn't exist</li>
<li><code>C-k</code> Cut a line, add it to the clipboard</li>
<li><code>C-y</code> Paste the contents of the clipboard</li>
<li><code>C-_</code> Undo</li>
<li><code>C-g</code> Abort a half-entered command</li>
</ul>
<p>You can also copy and paste using just the mouse. Using the left button, select a region of text to copy. Click the middle button to paste.</p>
<p>There are two ways you can use Emacs to develop Python code. The most straightforward way is to use it just as a text editor: create and edit Python files in Emacs; then run Python to test the code somewhere else, like in a terminal window. Alternatively, you can run Python inside Emacs: see the options under "Python" in the menubar, or type <code>C-c !</code> to start a Python interpreter in a split screen. (Use <code>C-x o</code> to switch between the split screens, or just click if C-x doesn't work).</p>
<p>If you want to spend some extra setup time becoming a power user, you can try an IDE like <a href="http://www.eclipse.org/downloads/">Eclipse</a> (Download the Eclipse Classic package at the bottom). Check out <a href="http://pydev.org/manual_101_root.html">PyDev</a> for Python support in Eclipse.</p>
</div>

<hr>

<div class="project">
<h2><a name="Installation"></a>Python Installation</h2>
<p>Many of you will not have Python 3.6 already installed on your computers. <a href="https://conda.io/docs/user-guide/overview.html">Conda</a> is an easy way to manage many different environments, each with its own Python versions and dependencies. This allows us to avoid conflicts between our preferred Python version and that of other
classes. We'll walk through how to set up and use a conda environment.</p>

<p> Prerequisite: <a href="https://docs.anaconda.com/anaconda/install/">Anaconda</a>. Many of you will have it installed from classes such as EE 16A; if you don't, install it through the link. </p>
<h4><a name="CreatingEnvironment"></a>Creating a Conda Environment</h4>
<p> Run the following command, and press y to install any missing packages. </p>
<div class="code_snippet">
<p><code>[cs188-ta@nova ~/python_basics]$ conda create --name cs188 python=3.6</code></p>
</div>

<h4><a name="EnteringEnvironment"></a>Entering the Environment</h4>
<p> To enter the conda environment that we just created, do the following. Note that the Python version within the environment is 3.6, just what we want. </p>
<div class="code_snippet">
<p><code>[cs188-ta@nova ~/python_basics]$ source activate cs188 <br> (cs188) [cs188-ta@nova ~/python_basics]$ python -V <br> Python 3.6.6 :: Anaconda, Inc.</code></p>
</div>

<h4><a name="LeavingEnvironment"></a>Leaving the Environment</h4>
<p> Leaving the environment is just as easy. </p>
<p><code>(cs188) [cs188-ta@nova ~/python_basics]$ source deactivate<br> [cs188-ta@nova ~/python_basics]$ python -V <br> Python 3.5.2 :: Anaconda custom (x86_64)</code></p>
<p>Our python version has now returned to whatever the system default is!</p>

<h4><a name="LabMachines"></a>Using the Lab Machines</h4>
<p>At the moment, students do not have the right permissions to download Python 3.6 or Conda on the lab machines. For P0, Python 3.5 (which is already installed) will suffice.</p>
</div>

<hr>

<div class="project">
<h2><a name="PythonBasics"></a>Python Basics</h2>
<h4>Required Files</h4>
<p>You can download all of the files associated with the Python mini-tutorial as a zip archive: <a href="./python_basics.zip">python_basics.zip</a>. If you did the unix tutorial in the previous tab, you've already downloaded and unzipped this file.</p>
<h4>Table of Contents</h4>
<ul>
<li><a href="#Invoking%20the%20Interpreter">Invoking the Interpreter</a></li>
<li><a href="#Operators">Operators</a></li>
<li><a href="#Strings">Strings</a></li>
<li><a href="#Dir%20and%20Help">Dir and Help</a></li>
<li><a href="#Built-in%20Data%20Structures">Built-in Data Structures</a></li>
<ul>
<li><a href="#Lists">Lists</a></li>
<li><a href="#Tuples">Tuples</a></li>
<li><a href="#Sets">Sets</a></li>
<li><a href="#Dictionaries">Dictionaries</a></li>
</ul>
<li><a href="#Writing%20Scripts">Writing Scripts</a></li>
<li><a href="#Indentation">Indentation</a></li>
<li><a href="#TabsSpaces">Tabs vs Spaces</a></li>
<li><a href="#Writing%20Functions">Writing Functions</a></li>
<li><a href="#Object%20Basics">Object Basics</a></li>
<ul>
<li><a href="#Defining%20Classes">Defining Classes</a></li>
<li><a href="#Using%20Objects">Using Objects</a></li>
<li><a href="#Static%20vs%20Instance%20Variables">Static vs Instance Variables</a></li>
</ul>
<li><a href="#Tips%20and%20Tricks">Tips and Tricks</a></li>
<li><a href="#Troubleshooting">Troubleshooting</a></li>
<li><a href="#More%20References">More References</a></li>
</ul>
<br>
<p>The programming assignments in this course will be written in <a href="http://www.python.org/about/">Python</a>, an interpreted, object-oriented language that shares some features with both Java and Scheme. This tutorial will walk through the primary syntactic constructions in Python, using short examples.</p>
<p>We encourage you to type all python shown in the tutorial onto your own machine. Make sure it responds the same way.</p>
<p>You may find the <a href="#Troubleshooting">Troubleshooting</a> section helpful if you run into problems. It contains a list of the frequent problems previous CS188 students have encountered when following this tutorial.</p>
<h4><a name="Invoking the Interpreter"></a>Invoking the Interpreter</h4>
<p>Python can be run in one of two modes. It can either be used <i>interactively</i>, via an interpeter, or it can be called from the command line to execute a <i>script</i>. We will first use the Python interpreter interactively.</p>
<p>You invoke the interpreter by entering <code>python</code> at the Unix command prompt.</p>
<div class="code_snippet"><p><code>(cs188) [cs188-ta@nova ~]$ python <br> Python 3.6.6 |Anaconda, Inc.| (default, Jun 28 2018, 11:07:29) <br> [GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)] on darwin <br> Type "help", "copyright", "credits" or "license" for more information. <br> &gt;&gt;&gt;</code></p></div>
<h4><a name="Operators"></a>Operators</h4>
<p>The Python interpreter can be used to evaluate expressions, for example simple arithmetic expressions. If you enter such expressions at the prompt (<code>&gt;&gt;&gt;</code>) they will be evaluated and the result will be returned on the next line.</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; 1 + 1 <br> 2 <br> &gt;&gt;&gt; 2 * 3 <br> 6 </code></p></div>
<p>Boolean operators also exist in Python to manipulate the primitive <code>True</code> and <code>False</code> values.</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; 1==0 <br> False <br> &gt;&gt;&gt; not (1==0) <br> True <br> &gt;&gt;&gt; (2==2) and (2==3) <br> False <br> &gt;&gt;&gt; (2==2) or (2==3) <br> True</code></p></div>
<h4><a name="Strings"></a>Strings</h4>
<p>Like Java, Python has a built in string type. The <code>+</code> operator is overloaded to do string concatenation on string values.</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; 'artificial' + "intelligence" <br> 'artificialintelligence' </code></p></div>
<p>There are many built-in methods which allow you to manipulate strings.</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; 'artificial'.upper()<br> 'ARTIFICIAL'<br> &gt;&gt;&gt; 'HELP'.lower()<br> 'help'<br> &gt;&gt;&gt; len('Help')<br> 4 </code></p></div>
<p>Notice that we can use either single quotes <code>' '</code> or double quotes <code>" "</code> to surround string. This allows for easy nesting of strings.</p>
<p>We can also store expressions into variables.</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; s = 'hello world' <br> &gt;&gt;&gt; print(s) <br> hello world <br> &gt;&gt;&gt; s.upper()<br> 'HELLO WORLD'<br> &gt;&gt;&gt; len(s.upper())<br> 11<br> &gt;&gt;&gt; num = 8.0 <br> &gt;&gt;&gt; num += 2.5 <br> &gt;&gt;&gt; print(num) <br> 10.5 </code></p></div>
<p>In Python, you do not have declare variables before you assign to them.</p>
<h4><a name="Dir and Help"></a> Exercise: Dir and Help</h4>
<p>Learn about the methods Python provides for strings. To see what methods Python provides for a datatype, use the <code>dir</code> and <code>help</code> commands:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; s = 'abc' <br><br> &gt;&gt;&gt; dir(s)<br> ['__add__', '__class__', '__contains__', '__delattr__', '__doc__', '__eq__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getslice__', '__gt__', '__hash__', '__init__','__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__','__repr__', '__rmod__', '__rmul__', '__setattr__', '__str__', 'capitalize', 'center', 'count', 'decode', 'encode', 'endswith', 'expandtabs', 'find', 'index', 'isalnum', 'isalpha', 'isdigit', 'islower', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'replace', 'rfind','rindex', 'rjust', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']<br><br> &gt;&gt;&gt; help(s.find)<br> </code> </p>
<pre><code>Help on built-in function find:<br>
find(...) method of builtins.str instance
    S.find(sub[, start[, end]]) -&gt; int

    Return the lowest index in S where substring sub is found,
    such that sub is contained within S[start:end].  Optional
    arguments start and end are interpreted as in slice notation.

    Return -1 on failure.<br>
</code></pre>
<p><code> &gt;&gt; s.find('b')<br> 1 </code></p></div>
<p>Try out some of the string functions listed in <code>dir</code> (ignore those with underscores '_' around the method name).</p>
<h4><a name="Built-in Data Structures"></a>Built-in Data Structures</h4>
<p>Python comes equipped with some useful built-in data structures, broadly similar to Java's collections package.</p>
<h4><a name="Lists"></a>Lists</h4>
<p><em>Lists</em> store a sequence of mutable items:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; fruits = ['apple','orange','pear','banana']<br> &gt;&gt;&gt; fruits[0] <br> 'apple' </code></p></div>
<p>We can use the <code>+</code> operator to do list concatenation:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; otherFruits = ['kiwi','strawberry']<br> &gt;&gt;&gt; fruits + otherFruits<br> &gt;&gt;&gt; ['apple', 'orange', 'pear', 'banana', 'kiwi', 'strawberry'] </code></p></div>
<p>Python also allows negative-indexing from the back of the list. For instance, <code>fruits[-1]</code> will access the last element <code>'banana'</code>:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; fruits[-2]<br> 'pear'<br> &gt;&gt;&gt; fruits.pop()<br> 'banana'<br> &gt;&gt;&gt; fruits<br> ['apple', 'orange', 'pear']<br> &gt;&gt;&gt; fruits.append('grapefruit') <br> &gt;&gt;&gt; fruits <br> ['apple', 'orange', 'pear', 'grapefruit'] <br> &gt;&gt;&gt; fruits[-1] = 'pineapple' <br> &gt;&gt;&gt; fruits <br> ['apple', 'orange', 'pear', 'pineapple'] </code></p></div>
<p>We can also index multiple adjacent elements using the slice operator. For instance, <code>fruits[1:3]</code>, returns a list containing the elements at position 1 and 2. In general <code>fruits[start:stop]</code> will get the elements in <code>start, start+1, ..., stop-1</code>. We can also do <code>fruits[start:]</code> which returns all elements starting from the <code>start</code> index. Also <code>fruits[:end]</code> will return all elements before the element at position <code>end</code>:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; fruits[0:2] <br> ['apple', 'orange'] <br> &gt;&gt;&gt; fruits[:3]<br> ['apple', 'orange', 'pear'] <br> &gt;&gt;&gt; fruits[2:]<br> ['pear', 'pineapple'] <br> &gt;&gt;&gt; len(fruits) <br> 4 </code></p></div>
<p>The items stored in lists can be any Python data type. So for instance we can have lists of lists:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; lstOfLsts = [['a','b','c'],[1,2,3],['one','two','three']] <br> &gt;&gt;&gt; lstOfLsts[1][2] <br> 3<br> &gt;&gt;&gt; lstOfLsts[0].pop()<br> 'c'<br> &gt;&gt;&gt; lstOfLsts<br> [['a', 'b'],[1, 2, 3],['one', 'two', 'three']]</code></p></div>
<h4>Exercise: Lists</h4>
<p>Play with some of the list functions. You can find the methods you can call on an object via the <code>dir</code> and get information about them via the <code>help</code> command:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; dir(list)<br> ['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', <br>'__delslice__', '__doc__', '__eq__', '__ge__', '__getattribute__', <br>'__getitem__', '__getslice__', '__gt__', '__hash__', '__iadd__', '__imul__', <br>'__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', <br>'__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', <br>'__rmul__', '__setattr__', '__setitem__', '__setslice__', '__str__', <br>'append', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', <br>'sort']<br> </code></p>
<pre>&gt;&gt;&gt; help(list.reverse)
Help on built-in function reverse:

reverse(...)
    L.reverse() -- reverse *IN PLACE*
</pre>
<p><code> &gt;&gt;&gt; lst = ['a','b','c']<br> &gt;&gt;&gt; lst.reverse()<br> &gt;&gt;&gt; ['c','b','a'] </code></p></div>
<p>Note: Ignore functions with underscores "_" around the names; these are private helper methods. Press 'q' to back out of a help screen.</p>
<h4><a name="Tuples"></a>Tuples</h4>
<p>A data structure similar to the list is the <em>tuple</em>, which is like a list except that it is immutable once it is created (i.e. you cannot change its content once created). Note that tuples are surrounded with parentheses while lists have square brackets.</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; pair = (3,5)<br> &gt;&gt;&gt; pair[0]<br> 3<br> &gt;&gt;&gt; x,y = pair<br> &gt;&gt;&gt; x<br> 3<br> &gt;&gt;&gt; y<br> 5 <br> &gt;&gt;&gt; pair[1] = 6<br> TypeError: object does not support item assignment </code></p></div>
<p>The attempt to modify an immutable structure raised an exception. Exceptions indicate errors: index out of bounds errors, type errors, and so on will all report exceptions in this way.</p>
<h4><a name="Sets"></a>Sets</h4>
<p>A <em>set</em> is another data structure that serves as an unordered list with no duplicate items. Below, we show how to create a set:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; shapes = ['circle','square','triangle','circle']<br> &gt;&gt;&gt; setOfShapes = set(shapes)<br>

</code></p></div>
<p> Another way of creating a set is shown below:
</p><div class="code_snippet"><p><code>
    &gt;&gt;&gt; setOfShapes = {‘circle’, ‘square’, ‘triangle’, ‘circle’}
</code></p></div>

<p> Next, we show how to add things to the set, test if an item is in the set, and perform common set operations (difference, intersection, union):</p>
<div class="code_snippet"><p><code>&gt;&gt;&gt; setOfShapes <br> set(['circle','square','triangle']) <br> &gt;&gt;&gt; setOfShapes.add('polygon') <br> &gt;&gt;&gt; setOfShapes <br> set(['circle','square','triangle','polygon']) <br> &gt;&gt;&gt; 'circle' in setOfShapes <br> True <br> &gt;&gt;&gt; 'rhombus' in setOfShapes <br> False <br> &gt;&gt;&gt; favoriteShapes = ['circle','triangle','hexagon']<br> &gt;&gt;&gt; setOfFavoriteShapes = set(favoriteShapes)<br> &gt;&gt;&gt; setOfShapes - setOfFavoriteShapes <br> set(['square','polyon']) <br> &gt;&gt;&gt; setOfShapes &amp; setOfFavoriteShapes <br> set(['circle','triangle'])<br> &gt;&gt;&gt; setOfShapes | setOfFavoriteShapes <br> set(['circle','square','triangle','polygon','hexagon']) </code></p></div>
<p><b>Note that the objects in the set are unordered; you cannot assume that their traversal or print order will be the same across machines!</b></p>
<h4><a name="Dictionaries"></a>Dictionaries</h4>
<p>The last built-in data structure is the <em>dictionary</em> which stores a map from one type of object (the key) to another (the value). The key must be an immutable type (string, number, or tuple). The value can be any Python data type.</p>
<p>Note: In the example below, the printed order of the keys returned by Python could be different than shown below. The reason is that unlike lists which have a fixed ordering, a dictionary is simply a hash table for which there is no fixed ordering of the keys (like HashMaps in Java). The order of the keys depends on how exactly the hashing algorithm maps keys to buckets, and will usually seem arbitrary. Your code should not rely on key ordering, and you should not be surprised if even a small modification to how your code uses a dictionary results in a new key ordering. <!--(see the <a href="/course/wiki/CS188/faq/">FAQ about dictionary key ordering</a>). --></p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; studentIds = {'knuth': 42.0, 'turing': 56.0, 'nash': 92.0 }<br> &gt;&gt;&gt; studentIds['turing']<br> 56.0<br> &gt;&gt;&gt; studentIds['nash'] = 'ninety-two'<br> &gt;&gt;&gt; studentIds<br> {'knuth': 42.0, 'turing': 56.0, 'nash': 'ninety-two'}<br> &gt;&gt;&gt; del studentIds['knuth']<br> &gt;&gt;&gt; studentIds<br> {'turing': 56.0, 'nash': 'ninety-two'}<br> &gt;&gt;&gt; studentIds['knuth'] = [42.0,'forty-two']<br> &gt;&gt;&gt; studentIds<br> {'knuth': [42.0, 'forty-two'], 'turing': 56.0, 'nash': 'ninety-two'}<br> &gt;&gt;&gt; studentIds.keys()<br> ['knuth', 'turing', 'nash']<br> &gt;&gt;&gt; studentIds.values()<br> [[42.0, 'forty-two'], 56.0, 'ninety-two']<br> &gt;&gt;&gt; studentIds.items()<br> [('knuth',[42.0, 'forty-two']), ('turing',56.0), ('nash','ninety-two')]<br> &gt;&gt;&gt; len(studentIds) <br> 3 </code></p></div>
<p>As with nested lists, you can also create dictionaries of dictionaries.</p>
<h4>Exercise: Dictionaries</h4>
<p>Use <code>dir</code> and <code>help</code> to learn about the functions you can call on dictionaries.</p>
<h4><a name="Writing Scripts"></a>Writing Scripts</h4>
<p>Now that you've got a handle on using Python interactively, let's write a simple Python script that demonstrates Python's <code>for</code> loop. Open the file called <code>foreach.py</code>, which should contain the following code:</p>
<div class="code_snippet">
<pre># This is what a comment looks like
fruits = ['apples', 'oranges', 'pears', 'bananas']
for fruit in fruits:
    print(fruit + ' for sale')

fruitPrices = {'apples': 2.00, 'oranges': 1.50, 'pears': 1.75}
for fruit, price in fruitPrices.items():
    if price &lt; 2.00:
        print('%s cost %f a pound' % (fruit, price))
    else:
        print(fruit + ' are too expensive!')
</pre>
</div>
<p>At the command line, use the following command in the directory containing <code>foreach.py</code>:</p>
<div class="code_snippet"><p><code> [cs188-ta@nova ~/tutorial]$ python foreach.py<br> apples for sale<br> oranges for sale<br> pears for sale<br> bananas for sale<br> apples are too expensive! <br> oranges cost 1.500000 a pound<br> pears cost 1.750000 a pound</code></p></div>
<p>Remember that the print statements listing the costs may be in a different order on your screen than in this tutorial; that's due to the fact that we're looping over dictionary keys, which are unordered. To learn more about control structures (e.g., <code>if</code> and <code>else</code>) in Python, check out the official <a href="https://docs.python.org/3.6/tutorial/">Python tutorial section on this topic</a>.</p>
<p>If you like functional programming <!--(like Scheme)--> you might also like <code>map</code> and <code>filter</code>:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; list(map(lambda x: x * x, [1,2,3]))<br> [1, 4, 9]<br> &gt;&gt;&gt; list(filter(lambda x: x &gt; 3, [1,2,3,4,5,4,3,2,1]))<br> [4, 5, 4] </code></p></div>
<p>The next snippet of code demonstrates Python's <em>list comprehension</em> construction:</p>
<div class="code_snippet">
<pre>nums = [1,2,3,4,5,6]
plusOneNums = [x+1 for x in nums]
oddNums = [x for x in nums if x % 2 == 1]
print(oddNums)
oddNumsPlusOne = [x+1 for x in nums if x % 2 ==1]
print(oddNumsPlusOne)
</pre>
</div>
<p>This code is in a file called <code>listcomp.py</code>, which you can run:</p>
<div class="code_snippet"><p><code> [cs188-ta@nova ~]$ python listcomp.py<br> [1,3,5]<br> [2,4,6] </code></p></div>

<h4>Exercise: List Comprehensions</h4>
<p>Write a list comprehension which, from a list, generates a lowercased version of each string that has length greater than five. You can find the solution in <code>listcomp2.py</code>.</p>
<h4><a name="Indentation"></a>Beware of Indendation!</h4>
<p>Unlike many other languages, Python uses the indentation in the source code for interpretation. So for instance, for the following script:</p>
<div class="code_snippet">
<pre>if 0 == 1:
    print('We are in a world of arithmetic pain')
print('Thank you for playing')
</pre>
</div>
<p>will output</p>
<div class="code_snippet"><code> Thank you for playing </code></div>
<p>But if we had written the script as</p>
<div class="code_snippet">
<pre>if 0 == 1:
    print('We are in a world of arithmetic pain')
    print('Thank you for playing')
</pre>
</div>
<p>there would be no output. The moral of the story: be careful how you indent! It's best to use four spaces for indentation -- that's what the course code uses.</p>
<h4><a name="TabsSpaces"></a>Tabs vs Spaces</h4>
<p>Because Python uses indentation for code evaluation, it needs to keep track of the level of indentation across code blocks. This means that if your Python file switches from using tabs as indentation to spaces as indentation, the Python interpreter will not be able to resolve the ambiguity of the indentation level and throw an exception. Even though the code can be lined up visually in your text editor, Python "sees" a change in indentation and most likely will throw an exception (or rarely, produce unexpected behavior).</p>
<p>This most commonly happens when opening up a Python file that uses an indentation scheme that is opposite from what your text editor uses (aka, your text editor uses spaces and the file uses tabs). When you write new lines in a code block, there will be a mix of tabs and spaces, even though the whitespace is aligned. For a longer discussion on tabs vs spaces, see <a href="http://stackoverflow.com/questions/119562/tabs-versus-spaces-in-python-programming">this</a> discussion on StackOverflow.</p>
<h4><a name="Writing Functions"></a>Writing Functions</h4>
<p>As in <!--Scheme or--> Java, in Python you can define your own functions:</p>
<div class="code_snippet">
<pre>fruitPrices = {'apples':2.00, 'oranges': 1.50, 'pears': 1.75}

def buyFruit(fruit, numPounds):
    if fruit not in fruitPrices:
        print("Sorry we don't have %s" % (fruit))
    else:
        cost = fruitPrices[fruit] * numPounds
        print("That'll be %f please" % (cost))

# Main Function
if __name__ == '__main__':
    buyFruit('apples',2.4)
    buyFruit('coconuts',2)
</pre>
</div>
<p>Rather than having a <code>main</code> function as in Java, the <code>__name__ == '__main__'</code> check is used to delimit expressions which are executed when the file is called as a script from the command line. The code after the main check is thus the same sort of code you would put in a <code>main</code> function in Java.</p>
<p>Save this script as <em>fruit.py</em> and run it:</p>
<div class="code_snippet"><p><code>(cs188) [cs188-ta@nova ~]$ python fruit.py<br> That'll be 4.800000 please<br> Sorry we don't have coconuts </code></p></div>
<!-- %%%%% -->
<h4>Advanced Exercise</h4>
<p>Write a <code>quickSort</code> function in Python using list comprehensions. Use the first element as the pivot. You can find the solution in <code>quickSort.py</code>.</p>
<h4><a name="Object Basics"></a>Object Basics</h4>
<p>Although this isn't a class in object-oriented programming, you'll have to use some objects in the programming projects, and so it's worth covering the basics of objects in Python. An object encapsulates data and provides functions for interacting with that data.</p>
<h4><a name="Defining Classes"></a>Defining Classes</h4>
<p>Here's an example of defining a class named <code>FruitShop</code>:</p>
<div class="code_snippet">
<pre>class FruitShop:

    def __init__(self, name, fruitPrices):
        """
            name: Name of the fruit shop

            fruitPrices: Dictionary with keys as fruit
            strings and prices for values e.g.
            {'apples':2.00, 'oranges': 1.50, 'pears': 1.75}
        """
        self.fruitPrices = fruitPrices
        self.name = name
        print('Welcome to %s fruit shop' % (name))

    def getCostPerPound(self, fruit):
        """
            fruit: Fruit string
        Returns cost of 'fruit', assuming 'fruit'
        is in our inventory or None otherwise
        """
        if fruit not in self.fruitPrices:
            return None
        return self.fruitPrices[fruit]

    def getPriceOfOrder(self, orderList):
        """
            orderList: List of (fruit, numPounds) tuples

        Returns cost of orderList, only including the values of
        fruits that this fruit shop has.
        """
        totalCost = 0.0
        for fruit, numPounds in orderList:
            costPerPound = self.getCostPerPound(fruit)
            if costPerPound != None:
                totalCost += numPounds * costPerPound
        return totalCost

    def getName(self):
        return self.name
</pre>
</div>
<p>The <code>FruitShop</code> class has some data, the name of the shop and the prices per pound of some fruit, and it provides functions, or methods, on this data. What advantage is there to wrapping this data in a class?</p>
<ol>
<li>Encapsulating the data prevents it from being altered or used inappropriately,</li>
<li>The abstraction that objects provide make it easier to write general-purpose code.</li>
</ol><br>
<h4><a name="Using Objects"></a>Using Objects</h4>
<p>So how do we make an object and use it? Make sure you have the <code>FruitShop</code> implementation in <code>shop.py</code>. We then import the code from this file (making it accessible to other scripts) using <code>import shop</code>, since <code>shop.py</code> is the name of the file. Then, we can create <code>FruitShop</code> objects as follows:</p>
<div class="code_snippet">
<pre>import shop

shopName = 'Russell House'
fruitPrices = {'apples': 1.00, 'oranges': 1.50, 'pears': 1.75}
uscShop = shop.FruitShop(shopName, fruitPrices)
applePrice = uscShop.getCostPerPound('apples')
print(applePrice)
print('Apples cost $%.2f at %s.' % (applePrice, shopName))

otherName = 'the Stanford Mall'
otherFruitPrices = {'kiwis':6.00, 'apples': 4.50, 'peaches': 8.75}
otherFruitShop = shop.FruitShop(otherName, otherFruitPrices)
otherPrice = otherFruitShop.getCostPerPound('apples')
print(otherPrice)
print('Apples cost $%.2f at %s.' % (otherPrice, otherName))
print("My, that's expensive!")
</pre>
</div>
<p>This code is in <code>shopTest.py</code>; you can run it like this:</p>
<div class="code_snippet">
<pre>[cs188-ta@nova ~]$ python shopTest.py
Welcome to the Russell House fruit shop
1.0
Apples cost $1.00 at the Russell House.
Welcome to the Stanford Mall fruit shop
4.5
Apples cost $4.50 at the Stanford Mall.
My, that's expensive!
</pre>
</div>
<p>So what just happended? The <code>import shop</code> statement told Python to load all of the functions and classes in <code>shop.py</code>. The line <code>berkeleyShop = shop.FruitShop(shopName, fruitPrices)</code> constructs an <em>instance</em> of the <code>FruitShop</code> class defined in <em>shop.py</em>, by calling the <code>__init__</code> function in that class. Note that we only passed two arguments in, while <code>__init__</code> seems to take three arguments: <code>(self, name, fruitPrices)</code>. The reason for this is that all methods in a class have <code>self</code> as the first argument. The <code>self</code> variable's value is automatically set to the object itself; when calling a method, you only supply the remaining arguments. The <code>self</code> variable contains all the data (<code>name</code> and <code>fruitPrices</code>) for the current specific instance (similar to <code>this</code> in Java). The print statements use the substitution operator (described in the <a href="https://docs.python.org/2/library/stdtypes.html#string-formatting">Python docs</a> if you're curious).</p>
<h4><a name="Static vs Instance Variables"></a>Static vs Instance Variables</h4>
<p>The following example illustrates how to use static and instance variables in Python.</p>
<p>Create the <code>person_class.py</code> containing the following code:</p>
<div class="code_snippet">
<pre>class Person:
    population = 0
    def __init__(self, myAge):
        self.age = myAge
        Person.population += 1
    def get_population(self):
        return Person.population
    def get_age(self):
        return self.age
</pre>
</div>
<p>We first compile the script:</p>
<div class="code_snippet"><p><code> [cs188-ta@nova ~]$ python person_class.py </code></p></div>
<p>Now use the class as follows:</p>
<div class="code_snippet"><p><code> &gt;&gt;&gt; import person_class<br> &gt;&gt;&gt; p1 = person_class.Person(12)<br> &gt;&gt;&gt; p1.get_population()<br> 1 <br> &gt;&gt;&gt; p2 = person_class.Person(63)<br> &gt;&gt;&gt; p1.get_population()<br> 2 <br> &gt;&gt;&gt; p2.get_population()<br> 2 <br> &gt;&gt;&gt; p1.get_age()<br> 12 <br> &gt;&gt;&gt; p2.get_age()<br> 63 </code></p></div>
<p>In the code above, <code>age</code> is an instance variable and <code>population</code> is a static variable. <code>population</code> is shared by all instances of the <code>Person</code> class whereas each instance has its own <code>age</code> variable.</p>
<!-- %%%% -->
<h4><a name="Tips and Tricks"></a>More Python Tips and Tricks</h4>
<p>This tutorial has briefly touched on some major aspects of Python that will be relevant to the course. Here are some more useful tidbits:</p>
<ul>
<li>Use <code>range</code> to generate a sequence of integers, useful for generating traditional indexed <code>for</code> loops:
<pre>for index in range(3):
    print(lst[index])
</pre>
</li>
<li>After importing a file, if you edit a source file, the changes will not be immediately propagated in the interpreter. For this, use the <code>reload</code> command: <code><br><br> &gt;&gt;&gt; reload(shop)<br> <br> </code></li>
</ul>
<h4><a name="Troubleshooting"></a>Troubleshooting</h4>
<p>These are some problems (and their solutions) that new Python learners commonly encounter.</p>
<ul>
<li>
<p><b>Problem:</b><br> ImportError: No module named py</p>
<p><b>Solution:</b><br> When using <code>import</code>, do not include the ".py" from the filename. <br> For example, you should say: <code>import shop</code> <br> NOT: <code>import shop<b>.py</b></code></p>
</li>
<li>
<p><b>Problem:</b><br> NameError: name 'MY VARIABLE' is not defined<br> Even after importing you may see this.</p>
<p><b>Solution:</b><br> To access a member of a module, you have to type <code>MODULE NAME.MEMBER NAME</code>, where <code>MODULE NAME</code> is the name of the <code>.py</code> file, and <code>MEMBER NAME</code> is the name of the variable (or function) you are trying to access.</p>
</li>
<li>
<p><b>Problem:</b><br> TypeError: 'dict' object is not callable</p>
<p><b>Solution:</b><br> Dictionary looks up are done using square brackets: [ and ]. NOT parenthesis: ( and ).</p>
</li>
<li>
<p><b>Problem:</b><br> ValueError: too many values to unpack</p>
<p><b>Solution:</b><br> Make sure the number of variables you are assigning in a <code>for</code> loop matches the number of elements in each item of the list. Similarly for working with tuples.</p>
<p>For example, if <code>pair</code> is a tuple of two elements (e.g. <code>pair =('apple', 2.0)</code>) then the following code would cause the "too many values to unpack error":</p>
<div class="code_snippet"><p><code>(a,b,c) = pair</code></p></div>
<p>Here is a problematic scenario involving a <code>for</code> loop:</p>
<div class="code_snippet"><pre>pairList = [('apples', 2.00), ('oranges', 1.50), ('pears', 1.75)]
for fruit, price, <em>color</em> in pairList:
    print('%s fruit costs %f and is the color %s' % (fruit, price, color))
</pre></div>
</li>
<li>
<p><b>Problem:</b><br> AttributeError: 'list' object has no attribute 'length' (or something similar)</p>
<p><b>Solution:</b><br> Finding length of lists is done using <code>len(NAME OF LIST)</code>.</p>
</li>
<li>
<p><b>Problem:</b><br> Changes to a file are not taking effect.</p>
<p><b>Solution:</b></p>
<ol>
<li>Make sure you are saving all your files after any changes.</li>
<li>
If you are editing a file in a window different from the one you are using to execute python, make sure you <code>reload(<i>YOUR_MODULE</i>)</code> to guarantee your changes are being reflected. <code>reload</code> works similarly to <code>import</code>.
</li>
</ol></li>
</ul>
<h4><a name="More References"></a>More References</h4>
<ul>
<li>The place to go for more Python information: <a href="http://www.python.org/">www.python.org</a></li>
<li>A good reference book: <a href="http://oreilly.com/catalog/9780596513986/">Learning Python</a> (From the UCB campus, you can read the whole book online)</li>
</ul>
</div>

<hr>

<div class="project">
<h2><a name="Autograding"></a>Autograding</h2>
<!--<p>All projects in this course will be autograded after you submit your code through the edX website. For all projects you can submit as many times as you like until the deadline. Every project's release includes its autograder for you to run yourself. This is the recommended, and fastest, way to test your code, but keep in mind you need to submit into the edX system to get your grade registered.</p>-->
<p>To get you familiarized with the autograder, we will ask you to code, test, and submit solutions for three questions. <!--You will submit your files on the last tab in this sequence (scroll up and click on the right most tab).--></p>
<p>You can download all of the files associated the autograder tutorial as a zip archive: <a href="./tutorial.zip">tutorial.zip</a> (note this is <b>different</b> from the zip file used in the UNIX and Python mini-tutorials, python_basics.zip). Unzip this file and examine its contents:</p>
<div class="code_snippet">
<pre>[cs188-ta@nova ~]$ unzip tutorial.zip
[cs188-ta@nova ~]$ cd tutorial
[cs188-ta@nova ~/tutorial]$ ls
addition.py
autograder.py
buyLotsOfFruit.py
grading.py
projectParams.py
shop.py
shopSmart.py
testClasses.py
testParser.py
test_cases
tutorialTestClasses.py
</pre>
</div>
<p>This contains a number of files you'll edit or run:</p>
<ul>
<li><code>addition.py</code>: source file for question 1</li>
<li><code>buyLotsOfFruit.py</code>: source file for question 2</li>
<li><code>shop.py</code>: source file for question 3</li>
<li><code>shopSmart.py</code>: source file for question 3</li>
<li><code>autograder.py</code>: autograding script (see below)</li>
</ul>
<p>and others you can ignore:</p>
<ul>
<li><code>test_cases</code>: directory contains the test cases for each question</li>
<li><code>grading.py</code>: autograder code</li>
<li><code>testClasses.py</code>: autograder code</li>
<li><code>tutorialTestClasses.py</code>: test classes for this particular project</li>
<li><code>projectParams.py</code>: project parameters</li>
</ul>
<p>The command <code>python autograder.py</code> grades your solution to all three problems. If we run it before editing any files we get a page or two of output:</p>
<div class="code_snippet">
<pre>[cs188-ta@nova ~/tutorial]$ python autograder.py
Starting on 1-21 at 23:39:51

Question q1
===========
*** FAIL: test_cases/q1/addition1.test
*** 	add(a,b) must return the sum of a and b
*** 	student result: "0"
*** 	correct result: "2"
*** FAIL: test_cases/q1/addition2.test
*** 	add(a,b) must return the sum of a and b
*** 	student result: "0"
*** 	correct result: "5"
*** FAIL: test_cases/q1/addition3.test
*** 	add(a,b) must return the sum of a and b
*** 	student result: "0"
*** 	correct result: "7.9"
*** Tests failed.

### Question q1: 0/1 ###


Question q2
===========
*** FAIL: test_cases/q2/food_price1.test
*** 	buyLotsOfFruit must compute the correct cost of the order
*** 	student result: "0.0"
*** 	correct result: "12.25"
*** FAIL: test_cases/q2/food_price2.test
*** 	buyLotsOfFruit must compute the correct cost of the order
*** 	student result: "0.0"
*** 	correct result: "14.75"
*** FAIL: test_cases/q2/food_price3.test
*** 	buyLotsOfFruit must compute the correct cost of the order
*** 	student result: "0.0"
*** 	correct result: "6.4375"
*** Tests failed.

### Question q2: 0/1 ###


Question q3
===========
Welcome to shop1 fruit shop
Welcome to shop2 fruit shop
*** FAIL: test_cases/q3/select_shop1.test
*** 	shopSmart(order, shops) must select the cheapest shop
*** 	student result: "None"
*** 	correct result: "&lt;FruitShop: shop1&gt;"
Welcome to shop1 fruit shop
Welcome to shop2 fruit shop
*** FAIL: test_cases/q3/select_shop2.test
*** 	shopSmart(order, shops) must select the cheapest shop
*** 	student result: "None"
*** 	correct result: "&lt;FruitShop: shop2&gt;"
Welcome to shop1 fruit shop
Welcome to shop2 fruit shop
Welcome to shop3 fruit shop
*** FAIL: test_cases/q3/select_shop3.test
*** 	shopSmart(order, shops) must select the cheapest shop
*** 	student result: "None"
*** 	correct result: "&lt;FruitShop: shop3&gt;"
*** Tests failed.

### Question q3: 0/1 ###


Finished at 23:39:51

Provisional grades
==================
Question q1: 0/1
Question q2: 0/1
Question q3: 0/1
------------------
Total: 0/3

Your grades are NOT yet registered.  To register your grades, make sure
to follow your instructor's guidelines to receive credit on your project.
</pre>
</div>
<p>For each of the three questions, this shows the results of that question's tests, the questions grade, and a final summary at the end. Because you haven't yet solved the questions, all the tests fail. As you solve each question you may find some tests pass while other fail. When all tests pass for a question, you get full marks.</p>
<p>Looking at the results for question 1, you can see that it has failed three tests with the error message "add(a,b) must return the sum of a and b". The answer your code gives is always 0, but the correct answer is different. We'll fix that in the next tab.</p>
</div>

<hr>

<div class="project">
<h2><a name="Q1"></a>Question 1: Addition</h2>
<p>Open <code>addition.py</code> and look at the definition of <code>add</code>:</p>
<div class="code_snippet">
<pre>def add(a, b):
    "Return the sum of a and b"
    "*** YOUR CODE HERE ***"
    return 0
</pre>
</div>
<p>The tests called this with <code>a</code> and <code>b</code> set to different values, but the code always returned zero. Modify this definition to read:</p>
<div class="code_snippet">
<pre>def add(a, b):
    "Return the sum of a and b"
    print("Passed a=%s and b=%s, returning a+b=%s" % (a,b,a+b))
    return a+b
</pre>
</div>
<p>Now rerun the autograder (omitting the results for questions 2 and 3):</p>
<div class="code_snippet">
<pre>[cs188-ta@nova ~/tutorial]$ python autograder.py -q q1
Starting on 1-21 at 23:52:05

Question q1
===========
Passed a=1 and b=1, returning a+b=2
*** PASS: test_cases/q1/addition1.test
*** 	add(a,b) returns the sum of a and b
Passed a=2 and b=3, returning a+b=5
*** PASS: test_cases/q1/addition2.test
*** 	add(a,b) returns the sum of a and b
Passed a=10 and b=-2.1, returning a+b=7.9
*** PASS: test_cases/q1/addition3.test
*** 	add(a,b) returns the sum of a and b

### Question q1: 1/1 ###

Finished at 23:41:01

Provisional grades
==================
Question q1: 1/1
Question q2: 0/1
Question q3: 0/1
------------------
Total: 1/3

</pre>
</div>
<p>You now pass all tests, getting full marks for question 1. Notice the new lines "Passed a=..." which appear before "*** PASS: ...". These are produced by the print statement in <code>add</code>. You can use print statements like that to output information useful for debugging. </p>

</div>

<hr>

<div class="project">
<h2><a name="Q2"></a>Question 2: buyLotsOfFruit function</h2>
<p>Add a <code>buyLotsOfFruit(orderList)</code> function to <code>buyLotsOfFruit.py</code> which takes a list of <code>(fruit,pound)</code> tuples and returns the cost of your list. If there is some <code>fruit</code> in the list which doesn't appear in <code>fruitPrices</code> it should print an error message and return <code>None</code>. Please do not change the <code>fruitPrices</code> variable.</p>
<p>Run <code>python autograder.py</code> until question 2 passes all tests and you get full marks. Each test will confirm that <code>buyLotsOfFruit(orderList)</code> returns the correct answer given various possible inputs. For example, <code>test_cases/q2/food_price1.test</code> tests whether:</p>
<div class="code_snippet"><code>Cost of [('apples', 2.0), ('pears', 3.0), ('limes', 4.0)] is 12.25</code></div>
<!--<p>Once your code passes all tests, <b>submit your code through the right most tab, to register your grades with us</b>. Verify that our autograder gives the same output as yours.</p>-->
</div>

<hr>

<div class="project">
<h2><a name="Q3"></a> Question 3: shopSmart function</h2>
<p>Fill in the function <code>shopSmart(orders,shops)</code> in <code>shopSmart.py</code>, which takes an <code>orderList</code> (like the kind passed in to <code>FruitShop.getPriceOfOrder</code>) and a list of <code>FruitShop</code> and returns the <code>FruitShop</code> where your order costs the least amount in total. Don't change the file name or variable names, please. Note that we will provide the <code>shop.py</code> implementation as a "support" file, so you don't need to submit yours.</p>
<p>Run <code>python autograder.py</code> until question 3 passes all tests and you get full marks. Each test will confirm that <code>shopSmart(orders,shops)</code> returns the correct answer given various possible inputs. For example, with the following variable definitions:</p>
<div class="code_snippet">
<pre>orders1 = [('apples',1.0), ('oranges',3.0)]
orders2 = [('apples',3.0)]
dir1 = {'apples': 2.0, 'oranges':1.0}
shop1 =  shop.FruitShop('shop1',dir1)
dir2 = {'apples': 1.0, 'oranges': 5.0}
shop2 = shop.FruitShop('shop2',dir2)
shops = [shop1, shop2]
</pre>
</div>
<p><code>test_cases/q3/select_shop1.test</code> tests whether:</p>
<div class="code_snippet"><p><code> shopSmart.shopSmart(orders1, shops) == shop1 </code></p></div>
<p>and <code>test_cases/q3/select_shop2.test</code> tests whether:</p>
<div class="code_snippet"><p><code>shopSmart.shopSmart(orders2, shops) == shop2 </code></p></div>
<!--<p>Once your code passes all tests, <b>submit your code through the right most tab, to register your grades with us</b>. Verify that our autograder gives the same output as yours.</p>-->
</div>

<hr>

<div class="project">
<h2><a name="Submission"></a> Submission</h2>
<p>In order to submit your project, please upload the following files to <b>Project 0 on Gradescope</b>: <code>addition.py</code>, <code>buyLotsOfFruit.py</code>, and <code>shopSmart.py</code>. Please <b>do not</b> upload the files
in a zip file or a directory as the autograder will not work if you do so.</p>

</div>

</div>
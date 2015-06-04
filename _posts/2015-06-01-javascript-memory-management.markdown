---
layout:     post
title:      "Memory management in JavaScript"
subtitle:   "Perormance optimizations by utilizing javascript memory management details"
date:       2015-06-01 12:00:00
author:     "Aditya Pratap Singh"
header-img: "img/post-bg-random-01.jpg"
---

<p>JavaScript as a language does not perform Garbage collection but this task is handled by browser. Whenever a webpage has some stuck-up effect, the reason behind is the browser performing Garbage collection behind the scene. </p>

<p>Since garbage collection in JavaScript is implicit and the algorithm for same is categorized as <a href="http://en.wikipedia.org/wiki/Decidability_%28logic%29" target="_blank">undecidable problem</a> , we can write our code in optimized way to perform optimized memory management. Some of the ways which can help in memory management in JavaScript are listed below:</p>

<ul>

  <li><b><i>Reuse objects as much as possible: </i></b> Changing the properties of same object instead of allocating a new object helps in reducing the garbage collection time </li>

  <li><b><i>Reuse existing arrays: </i></b> Emptying an array by assigning it to [] creates a new array instead of emptying existing one. To reuse an array, use array.length = 0 instead. </li>

  <li><b><i>Reuse existing function: </i></b> Functions which are being called again and again can be allocated memory by assigning to variable and then using the variable. E.g.: 

    <code> setInterval(function(){ alert("a");}, 1000); </code> <br/>
    can be rewritten as <br/>
    <code> var func = function(){ alert("a");};</br>
        setInterval(func, 1000);</code>
  </li>
</ul>

<p><strong> Garbage Collection:-</strong> As already mentioned, the problem to decide for garbage collection is categorized as undecidable problem, there are some constraints imposed to implement the same in browsers, as explained below:</p>

<ul>

  <li><b><i>References: </i></b> An object is said to reference other object if former has access to latter either explicitly or implicitly(via prototypes) </li>

  <li><b><i>Reference-counting garbage collection: </i></b> This is the most naive Garbage collection algorithm and states that an object is garbage collectable if there are no objects referencing it. E.g 
    <ul>
      <li>
	<comment>// object ‘obj’ created with 1 attribute</comment><br/>
	<code> var obj = { a: 'value1' }; </code>
      </li>
      <li>
	<comment>// 'obj2’ refers 'obj’. Hence 'obj’ cannot be Garbage collected yet</comment><br/>
	<code> var obj2 = obj;
	  obj = 0; </code>
      </li>
      <li>
	<comment>// 'obja’ has reference to attribute 'a’ of 'obj’</comment><br/>
	<code> var obja = obj.a; </code>
      </li>
      <li>
	<comment>// here 'obj’ can be garbage collected but since 'obja’ still has reference to 'obj.a’, garbage collection cannot be done on 'obj' </comment><br/>
	<code> obj2 = null; </code>
      </li>
      <li>
	<comment>// Now 'obj’ becomes a candidate for garbage collection</comment><br/>
	<code> obja = null; </code>
      </li>
    </ul>
  </li>
</ul>
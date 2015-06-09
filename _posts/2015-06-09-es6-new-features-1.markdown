---
layout:     post-dark
title:      "ES6 Introduction - Part 1"
subtitle:   "A brief overview to understand new features in ES6, including Strings, Objects, let"
date:       2015-06-01 12:00:00
author:     "Aditya Pratap Singh"
header-img: "img/post-bg-random-04.jpg"
---

<h2><i>Better String Support: </i></h2>

<p>The new addition to deck of ES 6 string methods are:</p>

<ul>

  <li><b><i> includes()- </i></b> returns true if given text is found anywhere inside the string else false </li>
  <li><b><i> startsWith() – </i></b> returns true if given text is found at the beginning of the string else false </li>
  <li><b><i> endsWith()- </i></b> returns true if given text is found at the end of the string else false </li>
  <li><b><i> Repeat() - </i></b> Accepts a single integer argument for the no of times to repeat the string </li>
</ul>

<iframe width="100%" height="300" frameborder="0" allowfullscreen src="http://www.es6fiddle.net/embed/iaplcqtx/"></iframe>

<h2><i>Better Object utilities: </i></h2>

<p><strong><i>Object.is():</i></strong> Better comparison using <code>Object.is()</code> and avoids the inaccuracy in identically equals operator (===) for below scenarios: </p> 

<ol>
  <li> (===) considers +0 and -0 as equal while Object.is() does not </li>
  <li> (===) returns (NaN === NaN) as false while Object.is treats all NaN as same and returns true </li>
</ol>

<iframe width="100%" height="300" frameborder="0" allowfullscreen src="http://www.es6fiddle.net/embed/iapkijp3/"></iframe>

<h2><i>Block Bindings using let: </i></h2> In most languages variables are created when declared while in JavaScript variables are hoisted at the top of function regardless of declaration. 
<a href="http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html"><i>variable hoisting</i></a> in JavaScript causes in bugs if we don’t understand the underlying logic of hoisting.

<p>To avoid this scenario and introduce the block level scope, ES 6 has introduced the <code>let</code> keyword.</p>

<p>The <code>let</code> keyword scopes the variable to current code block. </p>

<p><code>var: </code></p>
<iframe width="100%" height="300" frameborder="0" allowfullscreen src="http://www.es6fiddle.net/embed/iapkt8pv/"></iframe>

<p><code>let: </code></p>
<iframe width="100%" height="300" frameborder="0" allowfullscreen src="http://www.es6fiddle.net/embed/iapkuzte/"></iframe>

<p> One of the most important application of <code>let</code> can be observed in <code>for</code> loops where the loop control variable persists, even after the loop ends. </p>

<p>ES5:</p> 
<iframe width="100%" height="200" src="//jsfiddle.net/raL2y4L2/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
<iframe width="100%" height="300" frameborder="0" allowfullscreen src="http://www.es6fiddle.net/embed/iapllgu6/"></iframe>
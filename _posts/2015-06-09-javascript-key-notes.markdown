---
layout:     post
title:      "JavaScript: Key note on basics"
subtitle:   "The best practices on minute details ignored which cause bugs in code"
date:       2015-06-09 12:00:00
author:     "Aditya Pratap Singh"
header-img: "img/post-bg-random-2.jpg"
---
<p> Part 1 </p>

<p><strong>Objects:</strong>Except primitive types i.e. Numbers, strings, boolean, null and undefined , everything in JavaScript is object. Numbers, strings and booleans are like objects as they have methods but they are not mutable. Objects in JavaScript are always passed by reference and never copied.</p>

<p><strong>Global Abatement: </strong>Create a single global variable to remove pollution of global scope</p>

<p><strong>for in: </strong> The <code>for in</code> operator enumerates through all properties of an object including those from prototype chain and there is no guarantee on order of properties </p>

<p><strong>Object.keys: </strong> <code>Object.keys </code>is the equivalent of <code>for in</code> except that it iterates oly over property of current object and not the prototype chain</p>

<p><strong>Prototype: </strong> Prototype relation is dynamic i.e. updates to prototype are immediately reflected to all child objects. Update the prototype properties carefully. </p>


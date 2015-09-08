---
layout:     post
title:      "Lo-dash: Augment lodash with custom functions"
subtitle:   "Add your own custom methods or extend existing ones with custom behaviour"
date:       2015-09-07 10:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

<p>
<b><i>Lo-dash</i></b> provides a whole stack of cross-environment utility functions and focuses on performance aspects in javascript which is the key reason of high adoption of lo-dash.
But, at times the given set of utilities appear constrained for our usage. In such scenarios, we may want to update the existing method or add a new one to solve our purpose.
</p>

<p>
Let us take one such scenario and create a new function <code>$upsert</code> which mutates an array and update a given object in array based on passed criterion. 
This is a common scenario and to use this, we may have to create a function such as below and call it everytime using <code>_.bind </code>:
</p>
<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/3wLahfLv/3/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

<p>
<h4><b><i>_.mixin</i></b></h4>
A much better way is to add this method being called as part of the lo-dash library and use it on <code>_</code> object. <i>Lo-dash</i> provides a method <code>_.mixin</code>
for this. Let us see how we can use the above code to create the mixin and use it conveniently and even on function chains.
</p>

<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/9ocfbcof/1/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

<p> That's it! Using the same <code>_.mixin</code> method we can even decorate/ augment existing library methods. But, we should be cautious in doing so as it may have unwanted side-effects
 on parts of our code.</p>
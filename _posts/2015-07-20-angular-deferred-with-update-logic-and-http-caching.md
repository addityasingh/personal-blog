---
layout:     post
title:      "Angular Deferred: Update logic integrated with angular cache "
subtitle:   "Step by step implementation of decorating $q service to add update logic and integrate caching"
date:       2015-07-20 01:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

<h1>
	Step by step implementation of decorating <code>$q</code> service to add update logic and integrate caching using <code> angular-cache </code>
</h1>

<section> 
	<p>The <code>$q</code> service in angular provides a way to implement promises in angularjs. 
	But the issue with the service is that at times we may need a scenario where we need to resolve the promise twice.
	<br/>
	One example scenario would be to implement caching using <a class="custom-link" href="http://jmdobry.github.io/angular-cache/">angular-cache</a>, where we would want to fetch the data first from cache and simultaneously call the api to fetch the data.
	In this scenario we will have to resolve the promise twice: First while returning data from cache , Second when the data has been fetched from service api.
	
	We will see the step-by-step implementation of the scenario using <code> AugmentedDeferredService </code> service and <a class="custom-link" href="http://jmdobry.github.io/angular-cache/">angular-cache</a>. 
	</p>
	
	<ol>
		<li> Create an angular service <code>AugmentedDeferredService </code> which augments the behaviour of <code>$q</code> service. 
			In order to do so, we will add an <code> update()</code> method using a queue to track whether the promise has been resolved once.
	 	</li>
	 	<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/t5rw0drc/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
	 	<li> Add <code><a class="custom-link" href="http://jmdobry.github.io/angular-cache/">angular-cache</a></code> to your project </li>
	 	 <code> bower install angular-cache --save </code>
	 	 <li> Create an angular service CacheManager to manage the Caching logic for http requests. 
	 	 </li>
	 	 <iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/3676vgmm/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
	 	 <li> In order to use the above in controllers, you need to chain the  <code> update() </code> method after <code> then </code> method, as explained below </li>
	 	 <iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/g8joLfxv/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
	</ol>
	
	With the above steps, the workflow to implement caching embedded along side <code>http</code> requests is very inherent. 
</section>
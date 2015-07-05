---
layout:     post
title:      "Angular decorator: Add case insensitive urls to all routes"
subtitle:   "Use angular's provider decorator to add case insensitive behaviour"
date:       2015-07-06 01:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

Angular's provider is a way to add custom behaviour to the service instances. A nice explanation of difference between between provider, factory and service is given <a href="http://stackoverflow.com/a/15666049">here</a> by Misko Hevery.

Decorators (<code>provider.decorate()</code>) is a way to augment the provider with additional behaviour while configuring module, even before injecting it. 
<blockquote>A service decorator intercepts the creation of a service, allowing it to override or modify the behaviour of the service. The object returned by the decorator may be the original service, or a new service object which replaces or wraps and delegates to the original service. - <cite><a href="https://docs.angularjs.org/api/auto/service/$provide">docs.angularjs.org</a></cite></blockquote>

In order to make the url for a given path as insensitive angular router provides us with a property <code>caseInsensitiveMatch</code> which can be used as below to make a given path to make ot case insensitive.

<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/x7kbdeux/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

But the above approach is not very efficient if we want to make all the routes case-insensitive. Here comes decoratprs to the rescue. Using the <code>provider.decorate()</code> we can wrap the <code>$route</code> service provider to make the url case insensitive. Below decorator code snippet makes the routes case-insensitive. 

<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/v7fLjnsj/1/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Step wise description:
<ol>
	<li>
	We have created a basic angular app with config block
	</li>
	<li>
	Within the <code>config</code> function, we have injected the <code>$provide</code> service which is used to decorate the route service using <code>.decorate()</code> method on it
	</li>
	<li>
	The <code>.decorate()</code> function accepts 2 parameters: First parameter is name of service we want to decorate, in this case <code>$route</code>. Second parameter <code>extendRouteProvider</code> is a function which accepts parameter <code>$delegate</code> which is a delegate for service passed in first parameter.
	</li>
	<li>
	Within the <code>extendRouteProvider</code> function we have iterated over all the routes and updated 2 properties:
		<ol>
			<li><code>route.regexp</code>: make the regular expression for the path case insensitive </li> 
			<li><code>route.caseInsensitiveMatch</code>: Make the case insensitive matching property as <code>true</code></li>
		</ol>
	</li>
</ol>

That's it! All the routes now become case insensitive and will work just fine for both cases of path values. 

---
layout:     post
title:      "Integrate TypeScript, AngularJS using Gulp and Grunt"
subtitle:   "Start using typescript with existing angularjs application using grunt, gulp tasks"
date:       2015-07-15 10:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

<h1>
	Integrate TypeScript with AngularJS using <code>Gulp</code> and <code>Grunt</code>
</h1>
<p> TypeScript is gaining a lot of impetus due to its strong support for static typing in JavaScript and as a result is being adopted by all the major JavaScript frameworks including AngularJS, ReactJS and NodeJS. In order to integrate typescript we need a basic build task in our project to compile the typscript files to javascript. I have used both <code>gulp</code> and <code>grunt</code> to demonstrate the buld process for people using either of the 2.  </p>

<section>
	<p><code>Typescript</code> is compiled using the typescript compiler <code>tsc</code> . There are npm packages for both grunt and gulp which provides the <code>tsc</code> available to us. We will see both the packages and step by step demonstartion to integrate them.</p>

	<h3>Grunt</h3>
	<p><a class="custom-links" href="https://www.npmjs.com/package/grunt-typescript">grunt-typescript</a> is the <code>npm</code> package which provides the typescript's <code>tsc</code> compiler. The detailed options for using the task is mentioned <a href="https://www.npmjs.com/package/grunt-typescript#options">npm site</a>. We can see the very basic steps required to integrate the task with grunt here.</p>
	<ol>
		<li>
			Install the <code>grunt-typescript</code> npm package.
		</li>
		<code>npm install grunt-typescript --save</code>
		<br/>
		<li>
			Install the <code>tsd</code> package. This will be used for getting the TypeScript definition files <a class="custom-links" href="http://definitelytyped.org/">.tsd</a>, which provide type definitions for variables and members in TypeScript.
		</li>
		<code>npm install tsd --save</code> 
		<br/>
		<li>
			Install the typescript definition files for libraries being used. In my case, I was using angular so I have installed the tsd definition files for <code>angular and jquery</code>. jQuery is needed here as its a dependency required by angular.
		</li>
		<code> tsd install angular jquery </code>
		<br/>
		<li>
			Add a grunt task in <code>Gruntfile.js</code> to be used to compile typescript files. The detailed options can be explored <a class="custom-links" href="https://www.npmjs.com/package/grunt-typescript#options">here</a>
		</li>
		<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/9yq3dsbs/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
		<br/>
		<li>
			That's it. Add the task to your build tasks <code>default, serve, build, dev</code> as shown in above snippet and you are good to go.
		</li>
	</ol> 
	<br/>
	<br/>
	<br/>
	<h3>Gulp</h3>
	<p><a class="custom-links" href="https://www.npmjs.com/package/gulp-typescript">gulp-typescript</a> is a node package which makes the typescript compiler available as a module in gulp.</p>
	<ol>
		<li>
			Install the <code>gulp-typescript</code> npm package.
		</li>
		<code>npm install gulp-typescript --save</code>
		<br/>
		<li>
			Install the <code>tsd</code> package. This will be used for getting the TypeScript definition files <a class="custom-links" href="http://definitelytyped.org/">.tsd</a>
		</li>
		<code>npm install tsd --save</code> 
		<br/>
		<li>
			Install the typescript definition files for libraries being used. In my case, I was using angular so I have installed the tsd definition files for angular and jquery. jQuery is needed as its a dependency required by angular.
		</li>
		<code> tsd install angular jquery </code>
		<br/>
		<li>
			Add a gulp task in <code>gulpfile.js</code> to be used to compile typescript files. The detailed options can be explored <a class="custom-links" href="https://www.npmjs.com/package/grunt-typescript#options">here</a>. A sample task to compile typescript is shown as below.
		</li>
		<iframe width="100%" height="300" src="//jsfiddle.net/sublimejs/rthmjaey/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
	</ol>
	</section>
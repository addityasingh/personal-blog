---
layout:     post
title:      "AngularU conf: Discussion on Angular 2"
subtitle:   "Overview of AngularU, Web, TypeScript, and other tech discussed and points to note at the AngularU conference"
date:       2015-06-29 01:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

<p>The <a class="custom-links" href="https://angularu.com/ng/">AngularU conference</a> held in San Francisco between 22-25th June was a huge success. I have covered few of the important points that I got from the videos which are worth sharing. The Opening keynote was done by <i>Igor Minar, Brad Green and Misko Hevery</i>, the brains behind creating AngularJS. The events that followed on each of the days are listed below: </p>

<section>
<b><i>Day 1:</i></b> It was primarily focussed on <a class="custom-links" href="https://angular.io/">Angular 2 </a> and the new concepts which makes it different and better
<ol>
	<li>
		<b><i>Separation of application engine from Rendering engine:</i></b> By utilizing <a class="custom-links" href="http://www.html5rocks.com/en/tutorials/workers/basics/">Web workers</a> for all purposes, except for manipulating DOM, application engine has been separated from rendering engine. This has 2 obvious benefits: 
			<ul>
				<li>
					the speed is 3X of existing angular-1.x version
				</li>
				<li>
					It could use the same to leverage it for mobile and desktop along with web, similar to ReactJS
				</li>
			</ul>
	</li>
	<li>
		<div><b><i>Utilizes TypeScript:</i></b> <blockquote>TypeScript is a typed superset of JavaScript that compiles to plain JavaScript.-<cite> <a class="custom-links" href="http://www.typescriptlang.org/">TypeScript.com</a></cite></blockquote> <br/>
		Since Angular 2 is built on top of TypeScript, it lets us use the strong type system of TypeScript and features of ES6 (now ES2015) and ES7. I will cover more on TypeScript and ES6 in separate future articles, as they are huge interesting topics on themselves.</div>
	</li>
	<li>
		<b><i>Changed thinking for existing components:</i></b> I guess this will be the biggest change in the way we think about existing angular-1.x components. The major changes are:
			<ul>
				<li>
					<b><i>Removal of controllers:</i></b> Controllers will be totally removed and everyting will essentially be a component
				</li>
				<li>
					<b><i>Using classes instead of factories:</i></b> Services will be classes which could be injected as a dependency
				</li>
			</ul>
	</li>
	<li><b><i>Douglas Crockford's thoughts on Web</i></b>: The JavaScript guru shared his thoughts on Problems in Web and categorised them mainly into 2: InSecurity and Complexity
	</li>
</ol>
</section>

<section>

<b><i>Day 2:</i></b>
<ol>
	<li>
		<b><i>TypeScript by Jonathan Turner: </i></b> The second day illustrated the awsome features TypeScript has and the amount of developer headaches it removes while developing. There are discussions going on the implementation of async/await (An ES7 feature) in TypeScript.
	</li>
	<li>
		<b><i>Isomorphic JavaScript support:</i></b> The support for Isomorphic server side rendered angular is now possible in angular 2 using he angular 2 server plugin
	</li>
	<li>Ionic and Hybrid applications using angular</li>
	<li>Closing keynote by Steve Souders on web performance</li>
</ol>
</section>

<section>
<b><i>Day 3:</i></b>

<ul>
	<li>
		<b><i>Angular 2 with Microsoft technologies:</i></b> The third day started with Microsoft MVP, Andrew Connell's intro of Angular 2 introduction with Microsoft technologies TypeScript, Azure, O365. He also demonstrated the TypeScript Definition files .tsd by <a class="custom-links" href="https://github.com/DefinitelyTyped/tsd">DefinitelyTyped</a>  The whole lot of demos and content is available at Andrew's <a class="custom-links" href="https://github.com/andrewconnell/pres-enterprise-ng-mstech">github repo</a> 
	</li>
</ul>
</section>

<p>Reference: <a class="custom-links" href="https://angularu.com/ng/videos">angularu.com/ng/videos</a></p>
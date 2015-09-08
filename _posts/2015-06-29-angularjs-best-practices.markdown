---
layout:     post
title:      "AngularJS: Best practices"
subtitle:   "Best practices on writing Angular code for uniformity and performance"
date:       2015-06-29 10:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

<p> AngularJS has become one of the widely adopted javascript frameworks because of the vast benifits it provides in development lifecycle and code quality. With wide number of features it provides for a Single Page Application, their are some drawbacks to it in the way we use. I have discussed some of best practices to avoid the drawbacks of using angular:</p>

<section>
	<ol>
		<li>
			<b><i>Have a modular directory structure:</i></b> The directory structure is very important in organizing angular modules. This helps in not only organizing the code for everyone's understanding in team, but also good mainatinability and refactoring of code base. There are 2 mostly used app directory:
				<ul>
					<li><b><i> Component wise directories:</i></b> This pattern emphasizes on using one directory per component type i.e. 1 directory each for directives, services, controllers, filters etc. 
						<figure>
							<img src="/img/dist/app-components.png" alt="app-components" title="app-components" />
							<figcaption>app-compnents directory structure</figcaption>
						</figure>
					</li>
					<li> <b><i>Module wise directories</i></b>: This pattern emphasizes on using one directory per module. Every module will have sub-directory for services, controllers and directives. The common components can be moved to a common module
						<figure>
							<img src="/img/dist/app-modular.png" title="app-modular" alt="app-modular" />
							<figcaption>app-modular directory structure</figcaption>
						</figure>
					</li>
				</ul>
		</li>
		<li>
			<b><i> Single responsibility principle: One file should do only one task at a time </i></b> This gives us the advantage of finding the files easily and maintaining the code better. Also bugs are inevitable evils as part of development process. A better managed code with modules and components gives us advantage while debugging and triubleshooting for issues and fixing bugs.
		</li>
		<li>
			<b><i>Strictly follow MVC's SOC</i></b>:  The Separation of Concern(SOC) is a topic which has been discussed much in detail but still people miss out on them while working on applications. SInce Angular provides a very explicit MVC architecture, with help of <b><i> controllers, services, directives, config, routes etc. </i></b>, we should be keeping the task of each component to themselves.
		</li>
		<li>
			<b><i>Avoid explicit digest cycles:</i></b> Avoid using <code>$digest()</code> or <code>$apply()</code> method explicitly as they trigger a new <b><i>digest cycle</i></b>. Digest cycles evaluate all the scope variable for change in value i.e. <b><i>dirty checking</i></b> which in turn may trigger a sequence of digest cycles which is cost intensive in terms of app performance. 
		</li>
		<li>
			<b><i>Avoid using <code>$watch</code>:</i></b> Watchers monitor change in values and can be costly for app performance.
		</li>
		<li> 
			<b><i>Use angular's wrapper over DOM objects:</i></b> Use angular's wrappers <code> $window, $document, $timeout, $interval</code> etc. instead of <code>window, document, setTimeOut, setInterval </code>. This avoids explicit need of angular digest cycle to be called to apply changed scope values.
		</li>
		<li>
			<b><i>Use services to share values across controllers:</i></b> Avoid using <code>$watch, $rootScope </code> to share values across controllers. The impact of using <code>$watch </code> is mentioned in point above. Using <code>$rootScope</code> is like using a global variable across the app and should not be polluted.
		</li>
		<li>
			<b><i>Keep controllers as thin as possible:</i></b> Controllers represent the viewmodel for the view and should be kept as thin as possible. 
		</li>
		<li>
			<b><i>Move business logic and data fetching logic to services:</i></b> Retrieving data and storing data should be moved to skeleton services. Since controllers are plugged/unplugged based on route changes, they should not hold persistent data.
		</li>
		<li>
			<b><i>Use <code>ui-router</code> instead of <code>ng-router</code>: </i></b>  Since <code>ui-router</code> depicts the actual hierarchical structure of an app and it also retains the parent view data while navigating to sub-view. This allows for a smooth transition between parent and child views.
		</li>

	</ol>
	<b>Continued...</b>
</section>
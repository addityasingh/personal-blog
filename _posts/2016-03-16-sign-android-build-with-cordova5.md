---
layout:     post
title:      "Sign Android build with Cordova 5"
subtitle:   "Change the android apk signing mechanism, based on updates in Cordova 5"
date:       2016-03-16 21:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

The way we used to sign a Cordova/Ionic android build was to create a keystore and and the keystore, 
passwords to an `ant.properties` files as mentioned 
<a href='https://forum.ionicframework.com/t/ionic-toturial-for-building-a-release-apk/15758' class="custom-links" target="_blank"> here </a>.

But with the new version 5 of Cordova and onwards, it has changed and the new steps require the keystore to be specified 
as command-line variables or as a config file. 

The steps to sign the new way are:

<ol>
  <li>Add a keystore using:
<pre><code>keytool -genkey -v -keystore example.keystore -alias example -keyalg RSA -keysize 2048 -validity 10000 </code></pre>

  Note: This should be at root of project. Though not a hard requirement, it eases the file referencing
  </li>
  <br/>
  
  <li>Add a build.json with release/dev configuration for keystore, at the root of project:
<pre><code>
{
   "android": {
       "debug": {
           "keystore": "..\android.keystore",
           "storePassword": "android",
           "alias": "mykey1",
           "password" : "password",
           "keystoreType": ""
       },
       "release": {
           "keystore": "..\android.keystore",
           "storePassword": "",
           "alias": "mykey2",
           "password" : "password",
           "keystoreType": ""
       }
   }
}
</code></pre>
  </li>
  <br/>
  
  <li>Add the --buildConfig switch to Cordova/ Ionic build command:
<pre><code>cordova build android --release --buildConfig=build.json</code></pre>

or with Ionic as 
<pre><code>ionic build android --release --buildConfig=build.json</code></pre>
  </li>
<br />

The signed file will be generated under the new folder structure at <pre><code>/platforms/android/build/outputs/apk/android-release.apk</code></pre>
 
 

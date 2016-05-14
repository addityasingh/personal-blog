---
layout:     post
title:      "ES2015 code snippets using pure functions"
subtitle:   "Functional code snippets for commonly used utility methods using ES2015"
date:       2016-05-14 11:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

1. `map()`: Function to map a list to another. It uses ES2015 `de-structuring` and `spread operator (...)` 
  to access the elements of the list

      {% gist af83cc5037590bd4ca7ad3072342dd83 map.js %}
  

2. `len()`: Function to recursively calculate the length of a list. It uses ES2015 `de-structuring` and 
  `spread operator (...)` to access the elements of the list

      {% gist af83cc5037590bd4ca7ad3072342dd83 len.js %}
  
  
3. `range()`: Pure function to get the range of values from start to end. This uses the new `Array.from()` 
  method in ES2015 which accepts a array-like object as first parameter and optional `map()` function as second parameter

      {% gist af83cc5037590bd4ca7ad3072342dd83 range.js %}
  
  
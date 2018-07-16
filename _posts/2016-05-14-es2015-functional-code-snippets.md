---
layout:     post
title:      "ES2015 code snippets using pure functions"
subtitle:   "Functional code snippets for commonly used utility methods using ES2015"
date:       2016-05-14 05:00:00
author:     "Aditya Pratap Singh"
header-img: "img/dist/home-bg.jpg"
---

1. `map()`: Function to map a list to another. It uses ES2015 `de-structuring` and `spread operator (...)` 
  to access the elements of the list
```javascript
function map([first, ...rest], f) {
  if (!first) {
    return [];
  } else {
    return [f(first), ...map(rest, f)];
  }
}
```


2. `len()`: Function to recursively calculate the length of a list. It uses ES2015 `de-structuring` and 
  `spread operator (...)` to access the elements of the list
```
function len([first, ...rest]) {
  if (!first) {
    return 0
  } else {
    return 1 + len(rest);
  }
}
```
  
  
3. `range()`: Pure function to get the range of values from start to end. This uses the new `Array.from()` 
  method in ES2015 which accepts a array-like object as first parameter and optional `map()` function as second parameter

```
function range (start, end) {
  return Array.from({length: (end - start)}, (v, k) => k + start);
}
```

  
4. `forEach`:

```
function forEach(arr, callback, start=0) {
  if (0 < start && start < arr.length) {
    callback(arr[start], start, arr);
    return forEach(arr, callback, start + 1);
  }
}
```
  

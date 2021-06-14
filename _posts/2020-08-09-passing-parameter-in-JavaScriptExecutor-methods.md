---
layout: post
title: Regex Intro
date: 2020-08-09 13:32:20 +0300
description: Regex Intro
img: i-js1.png
fig-caption: # Add figcaption (optional)
tags: [regex]
---

In this post I will explain how we can pass a java parameter into the javascript method which is executed using the JavaScriptExecutor interface provided by ther selenium webdriver.

JavaScriptExecutor provides `executeScript` and `executeAsyncScript` methods to run any js script in the current page loaded by the selenium driver.
We might need to pass a parameter based on some logic to the function in the js from the java process. For example: if the user is authenticated, then pass a boolean parameter as true, if not then pass false to run a script which checks the numebr of notifications recieved by the usre on the notification page.
Providing sample code to achive this:

#### passing the param in the `executeScript` method:
Snippet from java method which calls the js function
```java
//todo: create driver instannce
boolean isAuthenticated = false;
//todo: set isAuthenticated using some logic
JavascriptExecutor javascriptExecutor = (JavascriptExecutor) driver;
InputStream in = getClass().getResourceAsStream("/auth-notification.js");
String js = IOUtils.toString(in, StandardCharsets.UTF_8);
javascriptExecutor.executeScript(js,  Boolean.toString(isAuthenticated))
```

#### Gettign the value in the js function:
Snippet fron `auth-notification.js` which we want to execute
```js
var is_authenticated = JSON.parse(arguments[0]);
if(is_authenticated){
  //do this
} else {
  //do this
}
```

---
layout: post
title: Enhancing Chrome Extension Functionality with Custom Headers
date: 2020-08-10 13:32:20 +0300
description: Enhancing Chrome Extension Functionality with Custom Headers
img: i-ce.png
fig-caption: # Add figcaption (optional)
tags: [chrome-extensions, javascript]
---

When building a Chrome extension, there may arise a need to customize the headers sent in a web request based on certain logic. Fortunately, the Chrome webRequest API equips developers with the ability to add listeners to requests before header exchange occurs. This empowers you to dynamically send custom headers based on your specific requirements. In this blog post, we'll explore how to achieve this feat with a practical example.

### Leveraging the Chrome webRequest API

The Chrome webRequest API opens up a world of possibilities for handling and modifying web requests. It enables you to intercept and manipulate requests, including adding custom headers. To get started, we'll create a Chrome extension that adds custom headers to specific requests.

### Practical Implementation

Consider a scenario where you want to send a custom header (custom-header: custom-header-value) with a request to a specific URL (https://url-update-here.com/). Here's how you can implement this in your Chrome extension.

*`background.js`*  
```js
chrome.webRequest.onBeforeSendHeaders.addListener(
    function (details) {
        //add your custom header here:
        if(details.url === "https://url-update-here.com/"){
            details.requestHeaders.push({name:"custom-header", value: "custom-header-value"})
        }
        return { requestHeaders: details.requestHeaders };
    },
    { urls: ['<all_urls>'] },
    [ 'blocking', 'requestHeaders', 'extraHeaders']
);
```
In this script, we use the `chrome.webRequest.onBeforeSendHeaders` event to add a listener. Within the listener function, we examine the request's URL and, if it matches our specified URL (https://url-update-here.com/), we add the custom header to the requestHeaders array.

*`manifest.json`*  
To complete our extension, we need to define its properties and permissions in the manifest.json file:
```json
{
    "name": "send Additional Headers",
    "version": "1.0",
    "description": "",
    "permissions": [
        "webRequest", 
        "webRequestBlocking",
        "<all_urls>"
    ],
    "background": {
      "scripts": ["background.js"]
    },
  
    "manifest_version": 2
  }
```
In the manifest.json file, we specify the extension's name, version, and description. We also declare the required permissions, including webRequest, webRequestBlocking, and `<all_urls>`. The background section indicates that our extension uses the `background.js` script.

### Wrapping Up

By following these steps, you can create a Chrome extension that dynamically adds custom headers to web requests based on your defined logic. Whether you need to authenticate, modify content types, or enhance security, this capability provides valuable flexibility when interacting with web services. We hope this guide proves helpful to anyone seeking a solution for sending custom headers in web requests through a Chrome extension. Happy coding!

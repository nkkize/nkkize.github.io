---
layout: post
title: Overriding items in local and session storage
date: 2020-09-15 13:32:20 +0300
description: Overriding items in local and session storage
img: i-storage.png
fig-caption: # Add figcaption (optional)
tags: [chrome-extensions, javascript]
---

This blog post talks about overriding the setItem function of localStorage and sessionStorage.
Since localStorage and sessionStorage are both instances of the Storage object, in order to override the setItem, you need to override the setItem of this interface.

### example.js
```js
    <script>
        (function () {
            const _setItemStorage = Storage.prototype.setItem;
            Storage.prototype.setItem = function (key, value) {
                if (this === window.localStorage) {
                    console.log("local storage key: " + key + " value: " + value);
                } else if (this === window.sessionStorage) {
                    console.log("session storage key: " + key + " value: " + value);
                }
                return _setItemStorage.apply(this, arguments);
            }
        })();
    </script>
```
Hope this helps anyone who is looking for overriding the setItem function of localStorage and sessionStorage.

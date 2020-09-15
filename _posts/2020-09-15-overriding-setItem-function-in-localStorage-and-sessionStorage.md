### Background
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

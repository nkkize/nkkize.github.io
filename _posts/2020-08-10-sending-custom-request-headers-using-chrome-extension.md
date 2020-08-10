### Background
This blog post talks about sending out custom headers in a web request based on some custom logic using chrome extension.

There might be a requirement where we need to send some custom headers to request a web page using a chrome extension.
the chrome webRequest API provides us the mechanism to add listeners on a request before the request headers are exchanged. 
We can add a listeners which can send out the custom headers based on any logic which you want to implement.
Below is the sample example of the `background.js` which matches a particular request url (you can add your cusotm logic here) and adds custom headers into the request.

### background.js
```js
chrome.webRequest.onBeforeSendHeaders.addListener(
    function (details) {
        for (var i = 0; i < details.requestHeaders.length; ++i) {
            if (details.requestHeaders[i].name === 'User-Agent') {
                details.requestHeaders.splice(i, 1);
                break;
            }
        }
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
### manifest.json

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
Hope this helps to anyone who is looking for a solution to send custom headers based some logic in a requst using chrome extension.

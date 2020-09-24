---
title: 'Fetch API'
date: 2019-12-12 16:21:14
category: 'development'
thumbnail: './images/education-system.png'
draft: false
---


## Fetch API for all your API calls

For years, XMLHttpRequest has been web developers’ trusted sidekick. Whether directly or under the hood, XMLHttpRequest has enabled Ajax and a whole new type of interactive experience, from Gmail to Facebook.

However, XMLHttpRequest is slowly being superseded by the Fetch API. Both can be used to make network requests, but the Fetch API is Promise-based, which enables a cleaner, more concise syntax and helps keep you out of callback hell.

The fetch() method is available in the global scope that instructs the browser to send a request to a provided URL.

How to Send a Request❔
```
fetch("url_to_fetch");
```

When you try running above code in console you can see that in network tab (in chrome dev tools) something is recieved from the url you provided but it's not displaying anywhere. It's because fetch is getting the data from url but we are not handling that data.

The fetch() method returns a Promise so you can use the then() and catch() methods to handle it.

```
fetch(url)
    .then(response => {
        // handle the response
    })
    .catch(error => {
        // handle the error
    });
```

When the request completes, the resource is available. At this time, the promise will resolve into a Response object.

The Response object is the API wrapper for the fetched resource. The Response object has a number of useful properties and methods to inspect the response.

we can convert this response to a json object by the following code.

```
fetch('/readme.txt')
    .then(response => response.json())
    .then(data => console.log(data));
    .catch(error => console.log(error));
```

A better version of the fetch api would be like this.
```
fetch(url)
  .then(response => response.json())
  .then(myData)
  .catch(e => handleError(e));
  
//now you can implement this functions which have data (myData) and error (handeError)
function myData(data){
  //json data from the API implemented
}

function hadleError(err){
  //handle the error here
}
```

The Fetch API is asynchronus so if you want it to be synchronus you need async await wrapper on fetch API to do so.

Happy Fetching!

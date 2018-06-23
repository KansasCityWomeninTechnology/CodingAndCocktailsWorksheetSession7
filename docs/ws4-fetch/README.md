# Fetch and APIs {#top}
Unless your web site is a static application, you will need to consume data from the back-end (server) via an API.

{% hint style='info' %}
**API (Application Programming Interface)** - Middle-woman that allows 2 applications to talk to each other [most often being the go-between for front-end and back-end].

**Static Application** - Website that only allows content changes, if you make them directly in the code, manually by _hand_.

**Dynamic Application** - Website that uses a server-side language, or JavaScript & APIs, to retrieve content from other files or a database to populate the site's content. Data in the database can be updated by a Content Management System (CMS) like WordPress, or via API interaction. This _dynamically_ updates the content, without the author or the programmer having to edit or write new code.
{% endhint %}

There are various ways to access data from an API. We're going to use JavaScript's built-in **fetch** method. When a user enters an **order name** and submits the order in our app, we'll first call [JSONPlaceholder](http://jsonplaceholder.typicode.com/) API to inspect JSON results then convert to use the [Unsplash API](https://source.unsplash.com/) to fetch an image randomly. 

{% hint style='info' %}
You might hear other JavaScript programmers talk about using [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest) (**X**ML**H**ttp**R**equest) or jQuery's [AJAX](https://www.w3schools.com/xml/ajax_intro.asp) (**A**synchronous **J**avaScript **A**nd **X**ML) to interact with APIs. Those were methods we had to use prior to ECMAScript 2015 (ES6). When ES6 came out, it included a native method **[fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)**, which was similar to jQuery's AJAX but doesn't require you to add a library like jQuery to use. You can use it in pure JavaScript!
{% endhint %}


<!-- trick markdown to give me a little space between these two sections of text -->
## 
This section will help guide you through the following steps:

{% include "./instruction-steps.html" %}


## Use fetch() to retrieve an image {#fetch} <span class="navigate-top"><a href="#top" title="Take me to the top of page"><i class="fa fa-chevron-circle-up" aria-hidden="true"></i></a></span>
We will call an API using `fetch` and log out the `json` response.
{% include "./1fetch.md" %}

## Connect the image to the DOM {#image} <span class="navigate-top"><a href="#top" title="Take me to the top of page"><i class="fa fa-chevron-circle-up" aria-hidden="true"></i></a></span>
Now let's try fetching an image and add the image to the web page.
{% include "./2image.md" %}

**Woohoo! Looking good!!**

<!-- trick markdown to give me a little space between these two sections of text -->
## 

## Checkpoint <span class="navigate-top"><a href="#top" title="Take me to the top of page"><i class="fa fa-chevron-circle-up" aria-hidden="true"></i></a></span>
Compare your _my-script.js_ against the answer key for your work so far. It might look a little different depending on spacing.  
{% include "./checkpoint.html" %}


<!-- trick markdown to give me a little space between these two sections of text -->
## 
## References and helpful links <span class="navigate-top"><a href="#top" title="Take me to the top of page"><i class="fa fa-chevron-circle-up" aria-hidden="true"></i></a></span>
[MDN Reference: fetch](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch)

[MDN Reference: Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

[MDN Reference: JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)

[MDN Reference: Blob](https://developer.mozilla.org/en-US/docs/Web/API/Blob)

[Chrome DevTools Network Reference](https://developers.google.com/web/tools/chrome-devtools/network-performance/reference)



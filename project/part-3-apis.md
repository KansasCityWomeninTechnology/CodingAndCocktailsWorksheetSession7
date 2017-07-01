# Part 3: Fetching APIs

### APIs & Fetch
Unless your web site is a static application, you are going to consume data from the back-end (server) via an API.

{% hint style='info' %}
**API (Application Programming Interface)** - Middle-woman that allows 2 applications to talk to each other [most often being the go-between for front-end and back-end].

**Static Application** - Website that only allows content changes, if you make them directly in the code, manually by _hand_.

**Dynamic Application** - Website that uses a server-side language, or JavaScript & APIs, to retrieve content from other files or a database to populate the site's content. Data in the database can be updated by a Content Management System (CMS) like WordPress, or via API interaction. This _dynamically_ updates the content, without the author or the programmer having to edit or write new code.
{% endhint %}

Let's learn how to access an API via JavaScript's built-in **fetch** method. We're going to use the Giphy API to fetch a gif based on the order name. That means we'll pass the API the order name. The API will provide that order name to the server, which will perform a search for a gif related to the order name. Once the server finds a relevant gif, it will supply that to the API, which will pass us the information we need for that gif. We'll then display the gif image on our Drink Order application.

{% hint style='info' %}
You might here other JavaScript programmers talk about using [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest) (**X**ML**H**ttp**R**equest) or jQuery's [AJAX](https://www.w3schools.com/xml/ajax_intro.asp) (**A**synchronous **J**avaScript **A**nd **X**ML) to interact with APIs. Those were methods we had to use prior to ECMAScript 2015 (ES6). When ES6 came out, it included a native method **[fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)**, which was similar to jQuery's AJAX but doesn't require you to add a library like jQuery to use. You can use it in pure JavaScript!
{% endhint %}

  1. In Atom in the _my-scripts.js_ file, on the line just above `$(document).ready`, you'll want to add a few empty lines, so you are ready to add our fetch method.

  2. We're going to create a function called `fetchGifByOrderName`, so add the following to the empty lines you added in step 1.

  ```
  var fetchGifByOrderName = function (orderName) {

  };
  ```

  3. Let's add a variable to hold the API URL on the first line of the method. Make sure you're inside the curly braces `{}` of the `fetchGifByOrderName` and type: ``var url = ``;``

  {% hint style='danger' %}
  Yes, those are back-ticks ` `` `  and not single quotes `''`. We'll cover why in the next step.
  {% endhint %}

  4. Now set the `url` variable to `https://api.giphy.com/v1/gifs/random?tag=${orderName}&api_key=75af32d089554f9a9daaac3f290e58fb` and instead of wrapping it with single quotes, we're going to wrap it with back-ticks. So it should look like this:

  ```
    var url = `https://api.giphy.com/v1/gifs/random?tag=${orderName}&api_key=75af32d089554f9a9daaac3f290e58fb`;
  ```

  {% hint style='tip' %}
  Previously, we used concatenation to combine strings with a `+`. The back-ticks allow us to use template literals, which is another way of concatenation.

  ```
  `https://api.giphy.com/v1/gifs/random?tag=${orderName}&api_key=75af32d089554f9a9daaac3f290e58fb`
  ```
  is the same as:
  ```
  'https://api.giphy.com/v1/gifs/random?tag=' + orderName + '&api_key=75af32d089554f9a9daaac3f290e58fb'
  ```

  Using a template literal (using back-ticks), we can use the `${}` format to wrap our variable `orderName`: `${orderName}`
  {% endhint %}

  {% hint style='info' %}
  TODO: Cover the parameters in the API & what they do
  {% endhint %}

  5. On a new line below the `url` variable (but still before `fetchGifByOrderName`'s closing `}`), let's type out the native **fetch** structure with some `console.log`s:

  ```
  fetch(url) // URL of API
		.then(function(response) {
			// Code for processing data response from API to desired data format
			return response.json();
		})
	  .then(function(response) {
	    // Code for using the data we formatted
			console.log(response);
	  })
	  .catch(function(error) {
	    // Code to run if API returns an error
      console.log(error);
	  });
  ```

  {% hint style='info' %}
  Let's walk through this method... TODO

  You don't technically have to indent the `.then` or `.catch` for the code to work, but indenting them makes your code easier to read as you can easily see they go with the `fetch(url)`.
  {% endhint %}

  At this point, your `fetchGifByOrderName` method should look similar to this:
  ![](/images/fetch-method.png)

  6. In order for this method to run, we need to call it somewhere. Scroll up in _my-scripts.js_ and look for the conditional you added earlier in the `submitOrder` method. You should have an `if` that checks that the `orderCount` is 5 or less. We want to call our method to fetch a gif **only** if the drink order can be ordered. Within the curly braces for the successful order condition (**not** if the `Drink order queue is full`), type: `fetchGifByOrderName(orderName);`. This will call our method & pass the value of the `orderName` variable through to our method.

  7. Let's try our API call out. Open (or refresh) your _index.html_ file in Chrome, and open the **Console** tab in Chrome's developer tools. From the Drink Order App, select a drink, type in a name & click **Order**.

  {% hint style='tip' %}
  Remember the shortcut to open dev tools in Chrome: `cmd + shift + i` (Mac) or `ctrl + shift + i` (Windows)
  {% endhint %}

  8. In the console, you should see 2 things logged. The value of the `orderName` variable (that we console logged earlier) and the JSON response from the API request, which will show collapsed like this:

  ![](/images/console-collapsed.png)

  Click on the little triangle to the left of `Object {data: Object, meta: Object}`, and then the little triangle next to `data: Object` and you can see the `data` tied to the gif, the giphy API is providing us:

  ![](/images/console-expanded.png)


### APIs & The Network Tab

The **Console** tab is great for general debugging, but there's another tab in developer tools that can be even more helpful when working with APIs. The **Network** tab.

  1. In your open dev tools, click on **Network** and click on the **Order** button in the app again. This will trigger a new API request that will show as a new request like:

  ![](/images/api-request-network-tab.png)

  2. Hover over the **Name** of the request (which is the API URL we requested), and it will appear like a link. Click on the name as a link, and you'll see a new set of sub-tabs open of **Headers**, **Preview**, **Response** & **Timing**.

  **Response** & **Preview** both show the API response. But **Preview** is in an easier ready format.

  ![](/images/network-api-response-tab.png)

  ![](/images/network-api-preview-tab.png)

  **Headers** shows you all the information that was sent in the API request (most of which is handled behind the scenes for you).

  ![](/images/network-api-headers-tab.gif)

  **Timing** does what it sounds like. It shows a breakdown of the request and response time.

  ![](/images/network-api-timing-tab.png)

  3. Check your work against the part three answer key here: TODO

**Way to go! You have increased your Wonder Woman power by 200%!!**

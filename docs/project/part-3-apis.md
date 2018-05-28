# Part 3: Fetching APIs

### APIs & Fetch
Unless your web site is a static application, you are going to consume data from the back-end (server) via an API.

{% hint style='info' %}
**API (Application Programming Interface)** - Middle-woman that allows 2 applications to talk to each other [most often being the go-between for front-end and back-end].

**Static Application** - Website that only allows content changes, if you make them directly in the code, manually by _hand_.

**Dynamic Application** - Website that uses a server-side language, or JavaScript & APIs, to retrieve content from other files or a database to populate the site's content. Data in the database can be updated by a Content Management System (CMS) like WordPress, or via API interaction. This _dynamically_ updates the content, without the author or the programmer having to edit or write new code.
{% endhint %}

There are various ways to access data from an API. We're going to use JavaScript's built-in **fetch** method. When a user enters an **order name** and submits the order in our Drink Order app, we'll use the [Giphy API](https://developers.giphy.com) to fetch a gif based on the **order name**. Here's how that interaction works:
- We pass the API the order name.
- The API provides the order name to the server.
- Server code searches a database for a gif related to the order name.
- When the server code finds a relevant gif, it provides the gif's details from the database to the API.
- The API returns the gif's details to us.
- We handle the API response.  
  Tonight, we will `console.log` the API response. But in the **Bonus** section of our worksheet, we display the gif image in the order details section of our Drink Order app.

{% hint style='info' %}
You might hear other JavaScript programmers talk about using [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest) (**X**ML**H**ttp**R**equest) or jQuery's [AJAX](https://www.w3schools.com/xml/ajax_intro.asp) (**A**synchronous **J**avaScript **A**nd **X**ML) to interact with APIs. Those were methods we had to use prior to ECMAScript 2015 (ES6). When ES6 came out, it included a native method **[fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)**, which was similar to jQuery's AJAX but doesn't require you to add a library like jQuery to use. You can use it in pure JavaScript!
{% endhint %}

  1. In Atom in the _my-scripts.js_ file, on the line just above `$(document).ready`, you'll want to add a few empty lines, so you are ready to add our fetch method.

  2. We're going to create a function called `fetchGifByOrderName`, so add the following to the empty lines you added in step 1:

  ```
  var fetchGifByOrderName = function (orderName) {

  };
  ```

  3. Let's add a variable to hold the API URL on the first line of the function. Make sure you're inside the curly braces `{}` of the `fetchGifByOrderName` and type: `var url = ``; `

  {% hint style='danger' %}
  Yes, those are back-ticks ` `` `  and not single quotes `''`. We'll cover why in the next step.
  {% endhint %}

  4. Now set the `url` variable to `https://api.giphy.com/v1/gifs/random?tag=${orderName}&api_key=75af32d089554f9a9daaac3f290e58fb`. It should look like this:

  ```
    var url = `https://api.giphy.com/v1/gifs/random?tag=${orderName}&api_key=75af32d089554f9a9daaac3f290e58fb`;
  ```

  {% hint style='tip' %}
  Previously, we used concatenation to combine strings with `+`. The back-ticks allow us to use template literals, which is another way of concatenation.

  `` `https://api.giphy.com/v1/gifs/random?tag=${orderName}&api_key=75af32d089554f9a9daaac3f290e58fb` ``

  is the same as:

  `'https://api.giphy.com/v1/gifs/random?tag=' + orderName + '&api_key=75af32d089554f9a9daaac3f290e58fb'`

  Using a template literal (using back-ticks), we can use the `${}` format (called a **template expression** or **template substitution**) to wrap our `orderName` variable: `${orderName}`
  {% endhint %}

  {% hint style='info' %}
  Let's break down the parts of the API URL & what they mean.
  `https://api.giphy.com/v1/gifs/random?tag=sandy&api_key=75af32d089554f9a9daaac3f290e58fb`

  **Scheme** - `http` or `https` - Most APIs will be secure and use `https`.  
  **Host** - `api.giphy.com` - This is the main domain of the URL.  
  **Path** - `/v1/gifs/random` - The part that follows the domain.  
    **Endpoint** - The unique part of the path, in this case `/gifs/random`. The **random** endpoint returns one gif based on the **tag** provided, but there are [other endpoints](https://developers.giphy.com/docs/#technical-documentation) available.  
  **Query Parameters** - These are at the end of the API URL & begin with a `?`, followed by one or more parameters in the format of `parameterName=value`. Usually the parameter name is **camelCase** and the value is a primitive value (boolean, number or string). Multiple parameters are separated by the ampersand: `&`.  
  <ul>
    <li> <strong>tag</strong> - The word(s) that will be used to search the Giphy database for a gif (<code>sandy</code> in our example above).</li>  
    <li><strong>api_key</strong> - Most APIs require some kind of authentication for users to be able to use the API. In the case of Giphy, they use an <code>api_key</code> parameter in the URL. To get an API key, you <strong>Create an App</strong> from <a href="https://developers.giphy.com" target="_blank">https://developers.giphy.com</a>. After providing a name and description of your app, Giphy provides you with an API key to use during development of your project. [Like what we're using tonight.] When you're ready to launch your project, you have to apply for a Production API key. We'll cover some differences in how APIs handle authentication in our <a href="https://www.eventbrite.com/e/coding-cocktails-september-tickets-33536482522?aff=julyWorksheet" target="_blank">September</a> session.</li>  
  </ul>
  {% endhint %}

  5. On a new line below the `url` variable (but still before `fetchGifByOrderName`'s closing `}`), let's type out the native **fetch** structure with some comments & `console.log`s:

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
  Let's walk through this method...

  On the first line, we're passing the `url` as a parameter to the `fetch` method that is built into JavaScript. The `fetch` method returns a **Promise** object.

  **Promises** allow you to control flow, like an if/else statement, but are great for when the conditional code is more complex and not right next to each other. We are unable to cover **Promises** in detail with the time we have tonight, but the important thing to know is that the **Promise** object has 2 methods available: `then` & `catch`. These methods are chainable - do this, **then** do this, **then** do this. `then` is for when the Promise is resolved successfully, whereas `catch` is for errors. Want to learn more about **Promises**? Read this [great article](https://scotch.io/tutorials/javascript-promises-for-dummies) later.

  When the fetch Promise is resolved (API is returned), the first `then` receives the API response, which is returned as a [Response object](https://developer.mozilla.org/en-US/docs/Web/API/Response). In order to get the data out of the Response object in the format we're expecting, we have to use one of the [Body methods](https://developer.mozilla.org/en-US/docs/Web/API/Body). The Giphy API is providing the data in JSON format, so we return the response using the `.json()` method, which also returns a Promise object.

  The second `then` is triggered when the first `then` finishes (when converting the response to JSON is done). The value returned by the first `then` is passed in as a parameter to the second `then`. At this point, the data is in JSON format, and ready for us to use in our application. For now, we're logging the JSON response format to the console.

  At the end, we have a `catch` method, so we can handle any errors thrown in the Promise resolution chain.

  You don't technically have to indent the `.then` or `.catch` for the code to work, but indenting them makes your code easier to read as you can easily see they go with `fetch(url)`.
  {% endhint %}

  At this point, your `fetchGifByOrderName` method should look similar to this:

  ![](/images/fetch-method.png)

  6. In order for this function to run, we need to call it somewhere. Scroll up in _my-scripts.js_ and look for the conditional you added earlier in the `submitOrder` method. You should have an `if` that checks that the `orderCount` is 5 or less. We want to call our function to fetch a gif **only** if the drink order can be ordered. Within the curly braces for the successful order condition (**not** if the `Drink order queue is full`), type: `fetchGifByOrderName(orderName);`. This will call our function & pass the value of the `orderName` variable through to our function.

  7. Let's try our API call out. Open (or refresh) your _index.html_ file in Chrome, and open the **Console** tab in Chrome's developer tools. From the Drink Order App, select a drink, type in a name & click **Order**.

  {% hint style='tip' %}
  Remember the shortcut to open dev tools in Chrome: `cmd + shift + i` (Mac) or `ctrl + shift + i` (Windows)
  {% endhint %}

  8. In the console, you should see 2 things logged. The value of the `orderName` variable (that we console logged earlier) and the JSON response from the API request, which will show collapsed like this:

  ![](/images/console-collapsed.png)

  Click on the little triangle to the left of `Object {data: Object, meta: Object}`, and then the little triangle next to `data: Object`. Now you can see the `data` for the gif that the Giphy API provided us:

  ![](/images/console-expanded.png)

  9. Check your work against the part three answer key here: [bit.ly/CnCPFKey3](http://bit.ly/CnCPFKey3).


### APIs & The Network Tab

The **Console** tab is great for general debugging, but there's another tab in developer tools that can be even more helpful when working with APIs. The **Network** tab.

  1. In your open dev tools, click on **Network** and click on the **Order** button in the app again. This will trigger a new API request that will show as a new request like:

  ![](/images/api-request-network-tab.png)

  2. Hover over the **Name** of the request (which is the API URL we requested), and it will appear like a link. Click on the name as a link, and you'll see a new set of sub-tabs open of **Headers**, **Preview**, **Response** & **Timing**.

  **Response** & **Preview** both show the API response. But **Preview** is in an easier to read format.

  ![](/images/network-api-response-tab.png)

  ![](/images/network-api-preview-tab.png)

  **Headers** shows you all the information that was sent in the API request (most of which is handled behind the scenes for you).

  ![](/images/network-api-headers-tab.gif)

  **Timing** does what it sounds like. It shows a breakdown of the request and response time.

  ![](/images/network-api-timing-tab.png)

  3. The Network tab doesn't capture API requests alone. If you refresh Chrome, with the **Network** tab selected, you'll see that it also captures all the files and assets that are loaded. There is a filter icon ![](/images/filter-icon.png) that toggles some optional filters on and off, when clicked. You can filter by JS files, CSS files, images, etc. This is great to troubleshoot whether a file loaded or not. API calls fall into the **XHR** category. Click on the **XHR** filter to see only the API call. If you don't see one, submit an order.

  ![](/images/network-tab-filter.gif)

**Way to go! You have increased your Wonder Woman power by 200%!!**

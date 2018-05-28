# Bonus!

If you’ve made it through all of the above or want to practice a little further at home, we have a couple bonuses for you!

## Bonus: Templates

We ended the main part of the worksheet with getting data from an API. Yay! Now what do we do with it? Let's add a simple template with image markup. Then we'll add our populated template to our Drink Order App, to display the gif to the user.

  1. Open _my_scripts.js_ in Atom & let's create a function named `addImageMarkup` below our closing `};` of the `fetchGifByOrderName` function, but above our `$(document).ready`:

  ```
  var addImageMarkup = function (response) {

  };
  ```

  2. On a newline between the `addImageMarkup`'s opening & closing curly braces, create a variable named `imageMarkup` and set it to a template literal using back-ticks `` `` ``: `var imageMarkup = ``; `

  3. Place your cursor in the middle of the back-ticks and hit the enter key two times. On the line that is blank between the back-ticks type:

  ```
  <div class="order-name-gif">
	  <img src="${}" alt="${}" title="${}" />
	</div>
  ```

  4. Since our data comes through in object format, let's use the dot notation we learned earlier in the worksheet to grab the data out of the response object. The `image_url` from the `data` portion of the response is what we want to use for our image's source. We'll do this first one together. Within the curly braces for the `src` attribute, type: `response.data.image_url`

  {% hint style='info' %}
  Here's an abbreviated sample of the response we get from the Giphy API:

  ```
  {
    "data": {
      "caption": "",
      "image_url": "http://media0.giphy.com/media/xT8qB5wdOO58pkkd7q/giphy.gif",
      "image_width": "245",
      "type": "gif"
    },
    "meta": {
      "msg": "OK",
      "response_id": "randomNumbersAndSymbols2378497248",
      "status": 200
    }
  }
  ```

  In order to determine what property we want & how to access it, it helps to work backward (or from inside out).

  The `image_url` is a property of the `data` object. And `data` is a nested object within our overall object.

  The outer curly braces are the `response` object (as that is what we're using as the parameter name in the `addImageMarkup` method). If we had `var addImageMarkup = function (funkyChicken)`, then our top-level object would be `funkyChicken` and we'd use `funkyChicken.data.image_url` to get the `image_url`. But `response` makes more sense than `funkyChicken`, so we'll leave it.
  {% endhint %}

  5. Use the previous step as a guide & within the curly braces for the `alt` & `title` attributes, add the `caption` from the JSON response. If you get stuck, check out the answer key at the end of this section or ask us on Slack!

  6. We're going to use jQuery to append our template literal to the markup (in the **order-details** id).

      1. Add a new line after the closing `` `; `` of the `imageMarkup` template literal variable (and before the closing `};` of the `addImageMarkup` method).

      2. On this new line, use jQuery to select the **order-details** id and use the `.append` method.

      3. Pass the `imageMarkup` as a parameter in the `.append()` method.

  7. We have our template added, but we're missing a step. Can you guess what it is?...  

  We need to pass the data to our template, so it can actually populate the template!  

  Look in the **fetch** method for where we're logging the response to the console. _Where we left a comment for using the formatted data._ Add a new line below the `console.log`, but above the closing `})` for that specific `then`.

  8. On this new line, call our `addImageMarkup` function by passing the `response` as a parameter.

  9. Refresh the Drink Order app in Chrome & place an order. You should see a gif appear below the text containing your drink order!

  {% hint style='tip' %}
  Not seeing a gif appear? Open the **Console** and **Network** tab to see if you can troubleshoot the issue. Grab a mentor on Slack, or check out the answer key below.
  {% endhint %}

  10. Check your work against the bonus answer key here: [bit.ly/CnCBonus1](http://bit.ly/CnCBonus1)

## Bonus: Fix a Bug

Try ordering a drink without entering a name.  

That’s not useful, is it? This is called a bug which is something you’ll run into regularly as a developer. Let’s fix that with another conditional!  These changes need to happen in _my-scripts.js_ in Atom.

1.  To fix this first use a conditional to check if the `orderName` variable has a value.  We just want the conditional to evaluate to true - an undefined value will always evaluate to the boolean value false. That means all we have to do to check whether or not `orderName` has a value is check `if (orderName) {`

2.  Wrap that if statement around the if statement that is checking our drink count.  This is called "nesting" if statements.  

    {% hint style='info' %}
It is bad practice to nest too many if statements since it decreases code readability which in turn makes maintenance more difficult.  It can also increase the potential for a bug or defect in your code since keeping track of what if branch you are in can be difficult when you get too many nested levels.
    {% endhint %}

3.  Trigger an alert if the `orderName` does not have a value.  It should say something like “Oops! Please enter your name to order your drink.”

4.  Save your changes and refresh the page in Google Chrome.  Try placing an order without a name now and see what happens!

5.  Compare with the bonus answer key here: [bit.ly/CnCBonus2](http://bit.ly/CnCBonus2)

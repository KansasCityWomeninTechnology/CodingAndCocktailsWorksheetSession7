# Fix a bug and add an enhancement

Let's practice what we learned by simulating project requirements. We have a bug to fix and add an enhancement to our drink order web app.

{% hint style='tip' %}
##### Hey Slacker!

Remember, we're here to help.
Join the KCWiT #codingandcocktails Slack Channel: [kcwit.slack.com](http://kcwit.slack.com)
{% endhint %}


## Fix a bug by using equality and conditional logic
You're getting ready to release the web page to your customer, Coding & Cocktails, and realize there's a bug! You can submit an order without a name. And if you submit an order without selecting a drink order, we see an error in the console. Let's check to make sure a name and a drink order exists before submitting the order.

1. Open Atom and start atom-live-server. Open Chrome DevTools in the browser tab that atom-live-server opens.
   {% hint style="tip" %}
Don't forget to save your file after each code change to see your web page reload. If another browser opens, you can open Chrome and open a tab using the same URL as the other browser tab.
   {% endhint %}

1. In _my-script.js_, inside the first `click` event handler, wrap the call to `submitOrder` in an `if` statement. Add an equality check for `orderName` variable is not empty in the `if` condition.
   {% hint style="working" %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Your code will look like this
<pre>
<code class="lang-javascript">
if (orderName) {
       submitOrder(orderName, drinkId);
}
</code>
</pre>
</details>
   {% endhint %}

   {% hint style="tip" %}
Remember, in JavaScript, `null`, `undefined`, and empty strings are **falsy**.
   {% endhint %}

1. Try submitting an order without the name. A drink order didn't submit. Yay! Now try submitting an order where the order contains only **whitespace** by using the spacebar to add one space in the order name. Uh oh.

1. We can use the built in `trim()` function to trim leading and trailing **whitespace** from user entry. The `trim()` function returns a new string without leading and trailing whitespace. We can add the call to `trim()` right after retrieving the value of the input element.Your code will look like this
   ```javascript
const orderName = document.getElementById('order-form-input').value.trim();
   ```

1. Try submitting an order with spaces as the name. A drink order didn't submit. Yay! We're getting closer! Now try submitting an order without the drink selected. Uh oh. We still see an error in the console: `Uncaught TypeError: Cannot read property 'id' of null`.
   {% hint style="working" %}
Look at the code to query for the radio button. We use `document.querySelector('input[type="radio"]:checked').id`. But if we don't select a drink, the `querySelector` can't find any elements matching a checked radio button. The return from `querySelector()` where no elements match the criteria is `null`. We then try to get the `id` property of `null`. We need to check the element is not `null` before proceeding.
   {% endhint %}

1. Change the variable name `drinkId` to `drinkElement` and remove the call to get the `id` property.
   {% hint style="working" %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Your code will look like this
<pre>
<code class="lang-javascript">
const drinkElement = document.querySelector('input[type="radio"]:checked');
</code>
</pre>
</details>
   {% endhint %}
   
1. We can now check if `drinkElement` is `null`. We can do this at the same time as the `if (orderName)` expression. We will use **logical operators**. We want both `orderName` and `drinkElement` to be truthy before calling `submitOrder`. We can use the **logical AND** operator: `&&`. Your `if` expression will look like this
   ```javascript
if (orderName && drinkElement)
   ```

1. Update the call to `submitOrder` to send the `id` of the `drinkElement` so that the `submitOrder` function still works.
   {% hint style="working" %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Your code will look like this
<pre>
<code class="lang-javascript">
submitOrder(orderName, drinkElement.id);
</code>
</pre>
</details>
   {% endhint %}

1. Try submitting a drink order without selecting a drink. Yay! A drink order was not submitted!


## Enhance the web app by adding a way to show a limited drink menu
Our bartender, Laura, doesn't want to have so many drinks available each session. She wants the ability to limit the drink menu to only show drinks she's prepared that evening. We will add a new property to the drink object and filter the array when building out the menu.

Here is another example where building out the menu programmatically allows us to easily add more functionality.

1. In _my-script.js_, in the `drinkArray`, add a new property to each drink object called `isAvailable`. The value is a **boolean** so set the values to `true` or `false`.
   {% hint style="working" %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Your drink object inside the array will look like this
<pre>
<code class="lang-javascript">
{
      'id': 'focusedLady',
      'label': 'Focused Lady',
      'photoId': 'eXdKs9d37Sc',
      'isAvailable': true
}
</code>
</pre>
Don't forget the single quotes and a comma between the <code>photoId</code> property and the new property. Make sure you add the property to every object!
</details>
   {% endhint %}

1. In the `buildDrinkMenu` method we want to create a new array of drinks where `isAvailable == true` and use that array to build the menu. We can do that using the built in `filter()` method on arrays. After the `fragment` variable declaration, but be before the `forEach`, create a new variable called `availableDrinks` and type the following code
   ```javascript
const availableDrinks = this.drinkArray.filter( (arrayElement) => {
      return arrayElement.isAvailable === true;
});
   ```
   {% hint style="working" %}
Let's walk through what we did here. We created a variable called `availableDrinks`. We access the `drinkArray` buy using `this` and iterate over each drink in `drinkArray` to apply the `filter` conditional. If `arrayElement.isAvailable == true`, that drink is added to `availableDrinks` array.
   {% endhint %}

1. Update the code to build the drink menu using the drinks in `availableDrinks`.
   {% hint style="working" %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Your code will look like this
<pre>
<code class="lang-javascript">
const availableDrinks = this.drinkArray.filter( (element) => {
      return element.isAvailable == true;
});

availableDrinks.forEach( (drink) => {
      ...
});
</code>
</pre>
</details>
   {% endhint %}

1. Does the drink menu show a subset of the drink array? Great job!!

<!-- trick markdown to give me a little space between these two sections of text -->
## 
**Way to stick with it!!**

![](https://media.giphy.com/media/QvBPuk3difuYU/giphy.gif)

<!-- trick markdown to give me a little space between these two sections of text -->
## 

## Checkpoint <span class="navigate-top"><a href="#top" title="Take me to the top of page"><i class="fa fa-chevron-circle-up" aria-hidden="true"></i></a></span>
Compare your _my-script.js_ against the answer key for your work so far. It might look a little different depending on spacing and photos you selected.  
{% include "./checkpoint.html" %}

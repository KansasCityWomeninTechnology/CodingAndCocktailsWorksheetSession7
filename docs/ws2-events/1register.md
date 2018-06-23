1. Inside the `document.addEventListener("DOMContentLoaded", ...)` function at the bottom of _my-script.js_, we defined a function for the `onclick` event for the order button. We want to change the way we listen to events by registering an event lister. Replace the `onclick` with
   ```javascript
document.getElementById('order-btn').addEventListener('click', function () {
      submitOrder(document.getElementById('order-form-input').value);
});
   ```
   {% hint style='info' %}
We are adding an event listener for 'click' events onto the DOM element with the id 'order-btn'. Upon clicking, we want the function to execute. The advantage of using `addEventListener` instead of `onclick` is that we can dynamically add and remove event listeners. We can also add mutiple listeners for the same event.
   {% endhint %}

1. Let's add another listener to the same event. After the `document.getElementById('order-btn')` function, press `Enter` to add a new line. Add another event listener for the same element id but this time log "second click handler" to the console.
      {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Add
<pre>
<code class="lang-javascript">
document.getElementById('order-btn').addEventListener('click', function () {
      console.log('second click handler');
});
</code>
</pre>
</details>
   {% endhint %}

1. Double check that everything still works when you interact with the button in Chrome. Do you see the second event handler log in the console as well as changes to the DOM from the `submitOrder` function?

1. It's about time to add the drink name to the order list. Change the `submitOrder` function to take `drink` as a second parameter.

1. We need to pass in the drink name into the `submitOrder` function. We can do that from the first 'order-btn' event listener function where we are passing in the order name, but the call to `submitOrder` is getting too cluttered. We can clean it up by querying the DOM and assigning the element values to a variable first. Declare a variable called `orderName` inside the first event handler function and assign it to the value of the form input. Your code should look like this
   ```javascript
const orderName = document.getElementById('order-form-input').value;
   ```

1. Let's do the same for the drink name. Declare a variable named `drinkName` after the variable `orderName` and assign it to value of the selected radio button by using the following code
```javascript
const drinkName = document.querySelector('input[type="radio"]:checked').value;
``` 
   {% hint style='info' %}
Notice how we queried for the radio buttons. We used `querySelector` to match by element tag and had to use a combination of single and double quotes. We can't use single quotes for the "radio" type since we used single quotes for the selector.
   {% endhint %}

1. Update the call to `submitOrder` in the event listener to pass in the `orderName` and `drinkName` variables. 
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Change <code>submitOrder(document.getElementById('order-form-input').value);</code> function to <code>submitOrder(orderName, drinkName);</code>
</details>
   {% endhint %}

1. In the `submitOrder` function update the string concatenation `name + " would like a drink!"` to include the drink name.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Change the <code>name + " would like a drink!"</code> function to
<code>name + " would like a " + drink</code>
</details>
   {% endhint %}

1. In Chrome, select a drink, add your name, and click the order button. Do you see the drink name included in the order? Select a different drink and click the order button again. Your drink order got replaced. How can we append to the new drink to the order instead of replacing it? 
   {% hint tip='tip' %}
You'll see an error if you don't select a drink. We'll fix this bug together in the Bonus assignment.
   {% endhint %}

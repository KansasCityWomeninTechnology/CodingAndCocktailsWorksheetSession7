1. In Atom, above the `submitOrder` function, declare a new variable using `let` named `numberOfDrinks` to count the number of drinks ordered. Assign it to the value 0. 

  {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Your variable will look like this:
<pre>
<code class="lang-javascript">
let numberOfDrinks = 0;
</code>
</pre>
</details>
   {% endhint %}

1. We want to increment the drink counter whenever someone submits an order. Increment `numberOfDrinks` as the first line inside `submitOrder` function. One way to do this is by adding `numberOfDrinks++;`.
   {% hint style='info' %}
We are incrementing `numberOfDrinks` by 1 using a shorthand method. This is functionally equivalent to either 
```javascript
numberOfDrinks = numberOfDrinks + 1;

numberOfDrinks += 1;
```
  {% endhint %}   

   {% hint style='tip' %}
Feel free to add `console.log()` statements to troubleshoot, double check your work, or to help reinforce concepts. You can also use the `debugger;` statement to **debug** your code using Chrome DevTools. Refer to the [debugging steps](https://codingandcocktailskc.gitbooks.io/session-6-programming-fundamentals-101-jquery-js/content/ws2-functions/#conditional) from last session or feel free to grab a mentor!
   {% endhint %}

1. Place your cursor after the closing curly brace for the `submitOrder` function, press `Enter` twice and create a new function called `updateOrderCount` that accepts one parameter: `count`. This time we're going to use arrow syntax to create the function.

  ```javascript
const updateOrderCount = (count) => {};
   ```

  Since this function is being created outside of existing functions that means it is created in the global scope.
   
   {% hint style="info" %}
In JavaScript, you can declare **functions** and **function expressions**. Function declarations use the syntax `function myFunction(){}` while function expressions use the syntax `const myFunction = function(){};`. In a function expression, you are assigning the function to a variable. This makes it easier to pass functions as parameters. We have been using **function expressions**.

The **arrow function** is a shorthand hand way to write function expressions and is an ECMAScript 2015 standard. When you use arrow functions, you pass parameters in the open and close parenthesis, just the same as a regular function. The `=>` symbol signifies the keyword `function`. 

Check out the references in this section to learn more about functions.

   {% endhint %}

1. In the _index.html_ file, find the section that displays the number of drinks ordered and make note of the HTML element's `id` attribute.

1. In _my-script.js_, inside the `updateOrderCount` function, select the element you found in the previous step using the `getElementById` method.   

1. Update the `innerHTML` of that HTML element by using string concatenation to build out the string "Drinks Ordered: 0" (except replace the "0" with the actual count).

   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Change the <code>updateOrderCount</code> function to
<pre>
<code class="lang-javascript">
const updateOrderCount = (count) => {
      document.getElementById('drink-count').innerHTML = "Drinks Ordered: " + count;
};
</code>
</pre>
</details>
   {% endhint %}

1. Add a call to the `updateOrderCount` function as the last line of the `submitOrder` function (right before the closing curly brace) so that we can see the drink count change. Make sure to pass in the `numberOfDrinks` as a parameter for the `updateOrderCount` function.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
In <code>submitOrder</code> function add the following code as the last line of the function 
<pre>
<code class="lang-javascript">
updateOrderCount(numberOfDrinks);
</code>
</pre>
</details>
   {% endhint %}

1. Click on the order button in Chrome. Do you see the drink counter change? 😎

   
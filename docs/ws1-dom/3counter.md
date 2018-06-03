1. Above the `submitOrder` function, declare a new variable using `let` named `numberOfDrinks` to count the number of drinks ordered. Assign it to the value 0. Your variable will look like this
   ```javascript
 let numberOfDrinks = 0;
   ```

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

1. Create a new function called `updateOrderCount` with parameter `count` in the global scope after the `submitOrder` function. This means you should create the new function outside of existing functions. We will use arrow syntax to create this function
   ```javascript
const updateOrderCount = (count) => {};
   ```
   {% hint style="info" %}
In JavaScript, you can declare **functions** and **function expressions**. Function declarations use the syntax `function myFunction(){}` while function expressions use the syntax `const myFunction = function(){};`. In a function expression, you are assigning the function to a variable. This makes it easier to pass functions as parameters. We have been using **function expressions**.

The arrow function is a shorthand hand way to write function expressions and is an ECMAScript 2015 standard.

Check out the references in this section to learn more about functions.

   {% endhint %}

1. Inside the `updateOrderCount` function, update the `innerHTML` of the HTML that will display the order count. Search for the `<h2>` element in _index.html_ with the text "Drinks Ordered: 0" to find the element id to use in your function. Use string concatenation to build out the same string exception replace "0" with the count. You will update the function in _my-script.js_.

   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Change the <code>updateOrderCount</code> function to
<code class="lang-javascript">
const updateOrderCount = (count) => {
      document.getElementById('drink-count').innerHTML = "Drinks Ordered: " + count;
};
</code>
</details>
   {% endhint %}

1. We need to call this new function so that we can see the drink count change. Call the `updateOrderCount` function as the last line of the `submitOrder` function, passing in the `numberOfDrinks` as a parameter. Your calling code should look like this
   ```javascript
updateOrderCount(numberOfDrinks);
   ```

1. Click on the order button in Chrome. Do you see the drink counter change? 😎

   
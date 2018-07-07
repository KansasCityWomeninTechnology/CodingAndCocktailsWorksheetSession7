1. In Atom, inside the `submitOrder` function in _my-script.js_ set up your if block structure to add conditional logic that will update the name for the order only on the first 4 orders. Remember an if block looks like this:
   ```javascript
if () {
      // Code goes here
}
   ```  

1. Add the condition inside the parentheses to specify what needs to be true for the code inside the `if` block to execute.  Remember we want the code to execute only for the first 4 orders.

1. Move the code that updates the `innerHTML` inside the if blocks curly braces.  Your code should now look similar to this:
```javascript
if (numberOfDrinks < 5) {
      document.querySelector('.order-details').innerHTML = name + " would like a drink!";
}
   ```

   {% hint style='working' %}
We can write the conditional logic using the '<=' operator. What would that look like?
   {% endhint %}

   {% hint style='tip' %}
Notice the indention on the `document.querySelector()`. Indent everything inside the `if` statement to make it easier to read your code. Doing so helps your brain group logical units of code together at a glance!
   {% endhint %}

1. In cases where there are more than 5 orders, we want to display an alert. Add an else condition with an alert that says "Drink order queue is full. Please try ordering again in a few minutes."
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Change the <code>if</code> statement to
<pre>
<code class="lang-javascript">
if (numberOfDrinks < 6) {
     document.querySelector('.order-details').innerHTML = name + " would like a drink!";
} else {
    alert("Drink order queue is full. Please try ordering again in a few minutes.");
}
</code>
</pre>
</details>
   {% endhint %}



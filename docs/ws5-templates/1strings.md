1. Inside the `updateOrderCount` function, update `innerHTML` text to use template literal instead of string concatenation. Template literals use backticks (\`\`) instead of quotes. Change the string to
   ```javascript
`Drinks Ordered: ${count}`;
   ```
   {% hint style='info' %}
Remember to change the single quotes to backticks!
   {% endhint %}

   {% hint style='working' %}
You can also use template literals to evaluate expressions. Change `${count}` to `${count + 10}`. Try ordering a drink and watch what happens to "Drinks Ordered" count. 😲 That's maybe too many drinks. Let's change it back to `${count}`.
   {% endhint %}

1. There's one more string to update. Inside the `submitOrder` method, we are using string concatenation to build the string `name + " would like a " + drink`. Change the string to use template literal.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Replace the string concatenation with 
<pre>
<code class="lang-javascript">
const textNode = document.createTextNode(`${name} would like a ${drink}`);
</code>
</pre>
</details>
   {% endhint %}

1. Inside the `if` statement in the `submitOrder` function, we'll programmatically add new HTML elements to append to the DOM. Create an `<h3>` element and assign it to a variable using the following code as the first line inside the `if` statement.
   ```javascript
let node = document.createElement('h3');
   ```
   {% hint style="working" %}
We want to create the following HTML using DOM manipulation
   ```html
<h3>
       Ada Lovelace would like a Focused Lady
</h3>
<h3>
       Grace Hopper would like a Nerdy Daiquiri
</h3>
   ```
   {% endhint %}

   {% hint style='info' %}
We are using the `Document` API to create a new `<h3>` element and assigning it to the variable `node`. We're using `let` to assign the variable instead of `const` because we need to modify the element. Variables declared with `const` are for read-only use.

We now have a structure that looks like `<h3></h3>`. There's no text inside yet.
   {% endhint %}

1. After creating the `<h3>` element, create a text node to house the text for the order detail using the code below. We can pass in the string concatenation to build the order detail into the text node.
   ```javascript
const textNode = document.createTextNode(name + " would like a " + drink);
   ```
   {% hint style="info" %}
We created a structure with only text but it's not attached to anything.
   {% endhint %}

1. Now we need to append the text node on to the element. We do this by calling `node.appendChild(textNode);`. 
   {% hint style="info" %}
We added the text as a child of the `<h3>` element to recreate HTML structure we want, but it's not attached to the DOM yet.
   {% endhint %}

1. Finally, we can append the node to the DOM element so that it shows up on the web page. We know what element to append because we queried and set the `innerHTML` earlier. Change the code from calling `innerHTML` to use `appendChild()`. You code should look like this
   ```javascript
document.querySelector('.order-details').appendChild(node);
   ```
1. Try ordering a few drinks on your web page using Chrome. Do you see each drink getting adding to the drink order list? 
   {% hint style='working' %}
We can also see the DOM getting updated in the **Elements** tab inside DevTools. You can inspect DOM elements by right clicking on the drink list and selecting **Inspect**. Ask a mentor to help you inspect DOM elements.
   {% endhint %}

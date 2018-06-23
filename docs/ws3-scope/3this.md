1. We want to iterate over `drinkArray` in the `buildMenu` method to build the drink menu. Remove the existing console log and instead log out `drinkArray`. The console log has an error stating "Uncaught ReferenceError: drinkArray is not defined". Uh oh. We can't access `drinkArray`?

1. In `buildDrinkMenu` method, change the console log statement to log `this.drinkArray`. 😮

1. What is up that!? Let's change the log statement to `console.log(this);`. The console log states that the output of "this" is the contents of the `menu` object. We see the `drinkArray` property with 8 elements in the array and the `buildDrinkMenu` function in the console log output. 
   {% hint style='working' %}
The `this` keyword provides the context from which we are working. In this case, it's the `menu` object. This is a tricky concept so you might need to explore a little to better understand what "this" is. What happens if you `console.log(this);` inside the second click handler? What is the "this" context? 

Note you'll see an error from the first click handler, but you'll still see the console log statements from the second click handler.

Arrow functions do not have their own `this` context so they are primarily used for small functions that don't require context complexity. 
   {% endhint %}

1. Now that we know how to access `drinkArray` from inside `buildDrinkMenu` function, iterate through the array and log each item out to the console. Your code will look like this
   ```javascript
buildDrinkMenu: function () {
      this.drinkArray.forEach( (drink) => {
            console.log(drink);
      });
 }
   ```

1. We're back in business. Let's build that drink menu out. We have to implement the code to build out the same HTML we commented out previously. Inside the `forEach`, remove the console log. Create a new `label` element and assign it to a variable by typing the following code
   ```javascript
let labelNode = document.createElement('label');
   ```
   {% hint style='working' %}
Our goal is to build an HTML element structure that looks like what you commented out in the HTML using JavaScript for each drink object in the array. We want to create something that looks like this using the drink's name and id:
```html
<label for="focusedLady">
      <input type="radio" id="focusedLady" name="drink" value="Focused Lady">
      Focused Lady
</label>
```

We now have the following HTML
```html
<label>
</label>
```
   {% endhint %}

1. We want a way to tie the radio button to the id of the drink we can do this by setting the attribute "for" and adding the id of the drink to it. This is it for the parent `label` tag. Add the following line code right after creating the `label` element
   ```javascript
labelNode.setAttribute('for', drink.id);
   ```
   {% hint style='info' %}
Notice we're accessing the 'id' property of the array element. The `for` attribute connects the visible label element to the input's `id` attribute. We are tying these two elements together using the drink id.

We now have
```html
<label for="focusedLady">
</label>
```
   {% endhint %}

1. Next we need to build the inner `<input>` element. After the `setAttribute` call, create a new element for `input` and assign it to a variable called `radioNode`. 
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Add <code>let radioNode = document.createElement('input');</code> after the previous <code>setAttribute</code> call in the <code>forEach</code>.
</details>
   {% endhint %}

1. We'll set the id of the `<input>` to the drink id and the value of the `<input>` to the drink label.  Add the following code after the `radioNode` declaration
   ```javascript
radioNode.id = drink.id;
radioNode.name = 'drink';
radioNode.setAttribute('type', 'radio');
radioNode.setAttribute('value', drink.label);
   ```
   {% hint style='info' %}
The input element is a radio button, so we add the `type` attribute and set it to `radio`. The `id` ties the radio button, the label, and the drink object together. The `name` is 'drink' for all elements. This ensures a user can select only one radio button at a time. Finally, the `value` attribute contains the drink object's label and helps display formatted text. 

We now have
```html
<input type="radio" id="focusedLady" name="drink" value="Focused Lady">
```
   {% endhint %}

1. Create the text node for the label and assign it to a variable called `textNode`.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Add <code>const textNode = document.createTextNode(drink.label);</code> after the previous <code>setAttribute</code> call in the <code>forEach</code> to create a node with the text for the drink name.
</details>
   {% endhint %}

1. Now we can start assembling the nodes. Add the `radioNode` and `textNode` to the `labelNode` like this
   ```javascript
labelNode.appendChild(radioNode);
labelNode.appendChild(textNode);
   ``` 
   {% hint style='info' %}
We are enclosing the radio button and the text inside the label to build the nested HTML element structure that looks like this
```html
<label for="focusedLady">
      <input type="radio" id="focusedLady" name="drink" value="Focused Lady">
      Focused Lady
</label>
```
   {% endhint %}

1. Now we need to add `labelNode` to the DOM. We can do so by building a separate DOM from the application via **DocumentFragment**. Inside the `buildDrinkMenu` function before the `forEach` call, declare a new variable
   ```javascript
let fragment = document.createDocumentFragment();
   ``` 
   {% hint style='info' %}
Building up a separate DOM and adding it to our main DOM tree when complete results in better performance. We can use the **Document** and **DocumentFragment** API to do this. Read more about **DocumentFragment** in the references for this section.
   {% endhint %}

1. Inside the `forEach` call, add `fragment.appendChild(labelNode);` as the last line to add the labelNode to the fragment DOM.

1. After the `forEach` call, add the fragment to the DOM by calling 
   ```javascript
document.querySelector('.radio-group').appendChild(fragment);
   ```
   {% hint style='info' %}
Why go through this effort instead of adding the drink list to the HTML? Because it's easier to add new drinks and edit the menu items. There are Javascript frameworks to help with making this process easier.
   {% endhint %}

1. Interact with your web app in Chrome. You should see the drink list and be able to place orders again!


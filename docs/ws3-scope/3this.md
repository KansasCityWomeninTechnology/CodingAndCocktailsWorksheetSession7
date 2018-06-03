1. We explored scopes on variables, but we don't need `numberOfDrinks` in the `buildDrinkMenu` function. Delete all the code inside the function and replace it with `console.log(drinkList);`. Uh oh. We can't access `drinkList`?

1. In `buildDrinkMenu` function, change the `console.log(drinkList);` to `console.log(this.drinkList);`. 😮

1. What is up that!? Let's change the log statement to `console.log(this);`. Log say "this" is the contents `menu` object. We can reference `drinkList` through it.
   {% hint style='working' %}
The `this` keyword provides the context from which we are working. In this case, it's the `menu` object. What happens if you `console.log(this);` inside a click handler? What is the "this" context? 
   {% endhint %}

1. Now that we know how to access `drinkList` from inside `buildDrinkMenu` function, iterate through the array and log each item out to the console. Your code will look like this
   ```javascript
this.drinkList.forEach( (drink) => {
      console.log(drink);
});
   ```

1. We're back in business. Let's build that drink menu out. We have to build out the same HTML we commented out previously in code. Inside the `forEach`, remove the console log. Create a new `label` element and assign it to a variable. Add the "radio" class to it by typing the following code
   ```javascript
let labelNode = document.createElement('label');
labelNode.className = 'radio';
   ```

1. We want a way to tie the radio button to the id of the drink we can do this by setting the attribute "for" and adding the id of the drink to it. This is it for the parent `label` tag. Add the following line code right after setting `className`
   ```javascript
labelNode.setAttribute('for', drink.id);
   ```
   {% hint style='info' %}
Notice we're access the 'id' property of the array element.
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

1. Create the text node for the label and assign it to a variable called `textNode`.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Add <code>const textNode = document.createTextNode(drink.label);</code> after the previous <code>setAttribute</code> call in the <code>forEach</code>.
</details>
   {% endhint %}

1. Now we can start assembling the nodes. Add the `radioNode` and `textNode` to the `labelNode` like this
   ```javascript
labelNode.appendChild(radioNode);
labelNode.appendChild(textNode);
   ``` 

1. Now we need to add `labelNode` to the DOM. We can do so by building a separate DOM from the application via DocumentFragment. Inside the `buildDrinkMenu` function before the `forEach` call, declare a new variable
   ```javascript
let fragment = document.createDocumentFragment();
   ``` 
   {% hint style='info' %}
Building up a separate DOM and adding it to our main DOM tree when complete results in better performance. We can use the Document and DocumentFragment API to do this.
   {% endhint %}

1. Inside the `forEach` call, add `fragment.appendChild(labelNode);` as the last line to add the labelNode to the fragment DOM.

1. After the `forEach` call, add the fragment to the DOM by calling 
   ```javascript
document.querySelector('.radio-group').appendChild(fragment);
   ```
   {% hint style='info' %}
Why go through this effort instead of adding the drink list to the HTML? It's easier to add new drinks and edit the menu items. There are Javascript frameworks to help with making this process easier.
   {% endhint %}


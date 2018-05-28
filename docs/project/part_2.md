# Part 2:  Loops, Arrays, and Objects

### Data Structures - Arrays & Objects 
First, you'll create a data structure in _my-scripts.js_. You’ll take the drinks from the HTML markup and move them into the javascript file so they are easier to change.  Since there are multiple drinks, an array (like a list) will be used to hold them.  Each drink will be a JavaScript object and will need two key value pairs; a value that will link the drink label and the radio button and a label that will display nicely.  There should be at least 5 drink objects in the menu.

  1. In Atom in the _my-scripts.js_ file just under the `var orderCount = 0;` code, create a variable called `cocktails` and initialize it to an empty array.  
  
  {% hint style='tip' %}
Empty Array: `[]`

Array with content of different data types: `[“element1” , “element2”, 3, true]`
  {% endhint %}

  2. Create an object for each drink.  
     * Each drink object will need two keys: `id` and `label`.
     * Each key will need a value paired with it.  
     * The `id` key will need a camelCase value that is the drink’s name paired with it.  This will connect the drink label to the radio button input.  

    {% hint style='tip' %}
camelCase means the first word starts with a lowercase letter and each subsequent word starts with an uppercase letter without spaces between words!
    {% endhint %} 
     
     * The `label` key will need the human readable drink name paired with it. 
     
  {% hint style='tip' %}
Objects are surrounded by curly braces and contain key-value pairs like this:
```
{
          "key": "value",
          "anotherKey": "Another Value"
}
```
  {% endhint %}

  {% hint style='tip' %}
Don’t forget the comma between key value pairs!
  {% endhint %}

  3.  Make sure to save your work even though we won’t see any cool changes just yet!

### Loops
Next, we need to create a function that will loop through the objects and add them to the menu

  1.  In Atom, in the _my-scripts.js_ file, just below that array of drink objects, create another function called `loadMenu`.  

  2.  Inside the `loadMenu` function body, add a for loop. 
  
  {% hint style='tip' %}
For loop example: 
`for (var i = 0; i < myArray.length; i++) { }`

In the Drink Order App code, `myArray` would be substituted with the `cocktails` array so the code loops through the array of drink objects.
  
The for loop has three pieces:

  1. The initializing expression - what number to start the loop with. `var i = 0;`
  
  2. The condition - how many times to run through the loop. `i < myArray.length;`
  
  3. The incrementing expression - how much to add to the loop counter each time through the loop. `i++` 
  {% endhint %}


  3.  Inside the body of the for loop (that means inside the curly braces!) add this code:
  ```$('.radio-group').append('<label class="radio" for="' + cocktails[i].id + '"><input type="radio" id="' + cocktails[i].id + '" name="drink" value="' + cocktails[i].label + '">' + cocktails[i].label + '</label>');```

  {% hint style='info' %}
This code is finding the HTML element that has the class `radio-group` applied to it.  Then it appends (or adds inside of that element) the label and radio input elements for the drink items. 

The label has a `class` attribute of `radio` for styling purposes.  There is also a `for` attribute that connects the visible label element to the input element’s `id` attribute. This is where using the `id` key’s value from the drink objects.

The input element is of type “radio” so it will be a radio button selector and all of them have the `name` attribute of "drink".  Having the same `name` across the radio input elements ensures the user can only select one radio button at a time. 

The last attribute is the `value` of the radio button which holds the drink objects `label` value and helps display formatted text.

Finally, inside the label HTML element, the drink object’s `label` value is used to display the formatted drink name text.
  {% endhint %}

  4.  Next, call this function so the menu gets loaded into the page. In Atom in the _my-styles.js_ file, add the function call on the first line inside the body of `$(document).ready(function() {`

  {% hint style='tip' %}
Look back at Part 1 for a reminder on how to call a function.
  {% endhint %}

  5.  In Atom, open the _index.html_ file so we can remove the drink menu markup so it will be loaded with our JavaScript instead of with the markup. Remove all of the `<label>` and `<input>` elements that are inside the following `div` element: `<div class="input-group radio-group">`.

  6.  In Atom, save both _index.html_ and _my-scripts.js_.
  
  7. In Google Chrome, reload your page.  
     It won’t look much different but you’ve utilized an array, objects, a for loop and a function to create different loading behavior!

  8.  Check your work against the part two answer key here: [bit.ly/CnCPFKey2](http://bit.ly/CnCPFKey2)

**Congratulations!  You worked through some hard stuff tonight!  Way to stick with it!**
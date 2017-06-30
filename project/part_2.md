# Part 2:  Loops, Arrays, and Objects

### Data Structures 
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
(camelCase means the first word starts with a lowercase letter and each subsequent word starts with an uppercase letter without spaces between words!)
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

  1.  Make sure to save your work even though we won’t see any cool changes just yet!

1.  Now we need a function that will loop through the objects and add them to the menu

  1.  Create another function called `loadMenu` in the **my-scripts.js** file in Sublime Text.  

  1.  Inside the function add a for loop. The for loop has three pieces, the initializing expression, the condition and the incrementing expression. That means we tell the loop where to start with the initializing expression, how many times we will need to loop with the condition and how much to add to the loop counter after each time through the loop. Here is a for loop example we’ll need to change ours to use our array’s variable name so we’re looping through our array of drink objects. 

      `for (var i = 0; i &lt; array.length; i++) { }`

  1.  Inside the for loop (that means inside the curly braces!) add this code:
    
      ``$('.radio-group').append('<label class=”radio” for="' + cocktails[i].id + '"><input type="radio" id="' + cocktails[i].id + '" name="drink" value="' + cocktails[i].label + '">' + cocktails[i].label + '</label>');``

        This code is finding the HTML element that has the class radio-group applied to it.  Then we are appending (or adding inside of that element) our label and radio input elements for the drink items. The label has a “class” attribute of radio for styling purposes.  There is also a “for” attribute that ties the label to the input element’s “id” attribute. This is where we are using the “id” key’s value from our drink objects.  

      The input element is of type “radio” so it will be a radio button selector and all of them have the “name” attribute of drink.  Having the same “name” across the radio input elements ensures the user can only select one radio button at a time. The last attribute is the value of the radio button which holds the drink objects “label” key’s value and helps us display formatted text.

      Finally, inside the label element we are utilizing the drink object’s “label” value to display the formatted drink name text.

  1.  Now we need to make sure this function is called so the menu gets loaded into the page. Add the function call just inside the `$(document).ready(function() {`

      1.  To call a function write the name of the function followed by open and close parentheses.  Inside the parentheses is where you would pass parameters to the function but since ours does not require parameters we just leave them empty. Example: `myFunction();`<br><br>

  1.  Finally we need to remove the markup from the **index.html** page so it will be loaded with our JavaScript instead of with the markup. Remove all of the label and input elements that are inside the div element with classes input-group and radio-group
  `<div class="input-group radio-group">`

  1.  Save both **index.html** and **my-scripts.js** and reload your page in Google Chrome.  It won’t look much different but you’ve utilized an array, objects, a for loop and a function to create different loading behavior!

1.  Check your work against the part two answer key here: [bit.ly/CnCPF2ndKey](http://bit.ly/CnCPF2ndKey)

**Congratulations!  You worked through some hard stuff tonight!  Way to stick with it!
**
1. In Atom, open _index.html_ and find the `div` tag containing the drink list. Comment out all the drinks listed inside the `div`, but don't comment the `div` tag itself. Save your _index.html_. We no longer see the drink list in Chrome and our web page is broken for the moment.
   {% hint style='working' %}
Highlight all the `<label>` elements inside the `div` with class "drink-menu" and select **Edit** <i class="fa fa-long-arrow-right"></i> **Toggle Comments**. You can also use the keyboard shortcut `ctrl` + `/` on Windows and `cmd` + `/` on Macs. Feel free to ask a mentor for help. 
   {% endhint %}
   {% hint style='tip' %}
Remember to use Atom to type code statements and Chrome to verify your work when your web page reloads. Don't forget to save _my-script.js_ every time you type a code statement.
   {% endhint %}

1. Let's create a new object. At the top of _my-script.js_, declare a new object called `menu` like this
   ```javascript
const menu = {};
   ```
   {% hint style="info" %}
Everything inside the `{}` is part of the object. The curly braces help group code statements together. We know the difference between objects and functions by the way we declare it. `const myObject = {};` is an object and `const myFunction = function(){};` is a function because use the `function` keyword.
   {% endhint %}

1. We want `menu` to handle menu related items, such as owning the list of drinks. Place your cursor between the opening and closing curly brace for the `menu` object and press `Enter`. Create a new property called `drinkArray` with an empty array. Your `menu` object should look like this
   ```javascript
const menu = {
    drinkArray: []
};
   ```
   {% hint style='info' %}
This creates an empty array called `drinkArray` as a property of `menu`.

Objects can contain properties and functions.
   {% endhint %}  

1. We want to populate `drinkArray` with the list of available drinks, which is everything with a radio button in front of it. To do so, each element in the array is an object with 2 properties: "id" and "label". We can add an object to the array like this
   ```javascript
const menu = {
    drinkArray: [{
      'id': 'focusedLady',
      'label': 'Focused Lady'
    }]
};
   ```
   {% hint style='info' %}
We can have objects inside other objects. Remember, we're grouping similar code statements together. So the inner object has information about a specific drink while the outer `menu` object has all information about the drink menu.

Objects can contain key-value pairs like this:
```javascript
{
          "key": "value",
          "anotherKey": "Another Value"
}
```

You can use single quotes, double quotes, or use no quotes when declaring keys in an object.
   {% endhint %}

1. Populate the rest of the `drinkArray` with the remaining drinks. Copy and paste the following code snippet to replace `drinkArray` to avoid typing fatigue. 
   ```javascript
const menu = {
    drinkArray: [{
            'id': 'focusedLady',
            'label': 'Focused Lady'
        },
        {
            'id': 'strongLady',
            'label': 'Strong Lady'
        },
        {
            'id': 'frontEndPunch',
            'label': 'Front-End Punch'
        },
        {
            'id': 'cachedOut',
            'label': 'Cached Out'
        },
        {
            'id': 'httPapaya',
            'label': 'httPAPAYA://'
        },
        {
            'id': 'nerdyDaiquiri',
            'label': 'Nerdy Daiquiri'
        },
        {
            'id': 'theAvernaCode',
            'label': 'The Averna Code'
        },
        {
            'id': 'focusedTheMostest',
            'label': 'Focused the Mostest'
        },
    ],
};
   ```
   {% hint style="info" %}
Notice a comma replaces the semicolon after the array declaration and we're not using quotes for the `drinkArray` property but are using single quotes for `id` and `label` properties inside each object within the array.
   {% endhint %}

1. Add a new property to the `menu` object called `buildDrinkMenu` with a log to console. This is a method on the object. A shortened version of the `menu` object will look like this
   ```javascript
const menu = {
    drinkArray: [{
            'id': 'focusedLady',
            'label': 'Focused Lady'
        },
        // other drinks here
    ],
    buildDrinkMenu: function () {
        console.log('inside buildDrinkMenu');
    }
};
   ```
   {% hint style='tip' %}
Defining responsibilities and grouping code for that purpose helps make code easier to maintain. In this case, adding a method `buildDrinkMenu` that contains the code needed to build out a drink menu makes it easier to know what area of code to look at when there is a bug in building the drink menu.
   {% endhint %}


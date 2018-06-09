1. At the top of _my-script.js_, declare a `const` array called `cocktails` using the code `const cocktails = [];`.
   {% hint style='info' %}
This creates an empty array called `cocktails` in the global scope.
   {% endhint %}  

   {% hint style='danger' %}
Don't forget to save your file after each code change!
   {% endhint %}
   
1. We want to populate `cocktails` with the list of available drinks, which is everything with a radio button in front of it. To do so, each element in the array is an object with 2 properties: "id" and "label". We can add an object to the array like this
   ```javascript
const cocktails = [{
      'id': 'focusedLady',
      'label': 'Focused Lady'
}];
   ```
   {% hint style='info' %}
Everything inside the `{}` is part of the object. The curly braces help group code statements together. We know the difference between objects and functions by the way we declare it. `const myObject = {};` is an object and `const myFunction = function(){};` is a function.

Objects contain key-value pairs like this:
```javascript
{
          "key": "value",
          "anotherKey": "Another Value"
}
```
   {% endhint %}

1. Populate the rest of the `cocktails` array with the list of the available drinks. Copy and paste the following code snippet to replace the cocktails array declaration to avoid typing fatigue. 
   ```javascript
const cocktails = [{
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
];
   ```
   {% hint style='info' %}
Notice commas separate array elements.
   {% endhint %}

1. In Atom, open _index.html_ and find the div containing the drink list. Comment out all the drinks. Save your _index.html_. We no longer see the drink list in Chrome and our web page is broken for the moment.
   {% hint style='working' %}
Highlight all the `<label>` elements inside the `div` with class "drink-menu" and select **Edit** <i class="fa fa-long-arrow-right"></i> **Toggle Comments**. You can also use the keyboard shortcut `ctrl` + `/` on Windows and `cmd` + `/` on Macs. Feel free to ask a mentor for help. 
   {% endhint %}

1. In Atom, open _my-script.js_ and navigate to the bottom of the file. Inside the `document.addEventListener("DOMContentLoaded", ...)` function, before the calls to register the event listeners for the order button, iterate over the `cocktails` array and log each element to the console using the following code
   ```javascript
cocktails.forEach( (item) => { console.log(item);});
   ```

1. In Chrome, take a look at the console to see what we logged. We logged out each object with the properties `id` and `label`. Back in Atom, edit `console.log(item);` to `console.log(item.label);`. Now what do you see in the console? 
   {% hint style='info' %}
We can access properties inside objects using the `.` notation. We can't access `label` without first going through the object.
   {% endhint %}

1. Let's create a new object. At the top of _my-script.js_ after the declaration for `cocktails` array, declare a new object called `menu` like this
   ```javascript
const menu = {}
   ```
   {% hint style='info' %}
Notice there's no semicolons after object declarations.
   {% endhint %}

1. We want to declare the `cocktails` array inside the `menu` object. Place your cursor between the opening and closing curly brace for the `menu` object and press `Enter`. Create a new property called 'drinkArray' and paste the array as the value of the property. Your `menu` code should look like this
   ```javascript
const menu = {

    // 3.1.6
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
}
   ```
   {% hint style="info" %}
Notice a comma replaces the semicolon after the array declaration and we're not using single quotes for the property name this time.
   {% endhint %}

1. Add a new property to the `menu` object called `buildDrinkMenu` with a log to console. This will be a method on the object. A shortened version of the `menu` object will look like this
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
}
   ```


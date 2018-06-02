1. declare array of objects called cocktails

1. comment out code in html (comment out all `<label>` inside the div with class "drink-menu") 

1. iterate over cocktails array as first line inside "DOMContentLoaded" using forEach
    `cocktails.forEach( (drink) => { console.log(drink)});

1. Look at what console writes out. Edit to console.log(drink.label)
   * hint about accessing properties in an object

1. Create named object called 'menu' after the declaration of cocktails array
   `const menu = {}`
   * Hint- notice no semicolon

1. Add a new property to menu for list of drinks move array declaration. 
```javascript
const menu = {
    drinkList: [{'id': 'focusedLady', 'label': 'Focused Lady'}]
}
   ```
   * Add a hint about what is going on here

1. Add a new property to define a function called `buildDrinkList`. We will build out the drink menu
   ```javascript
const menu = {
    drinkList: [{'id': 'focusedLady', 'label': 'Focused Lady'}],
    buildDrinkList: function() {
        console.log('inside buildDrinkList');
    }
}
   ```
  

1. In Atom, open _my-script.js_ and navigate to the bottom of the file. Inside the `document.addEventListener("DOMContentLoaded", ...)` function, before the calls to register the event listeners for the order button, iterate over the `drinkArray` and log each element to the console using the following code
   ```javascript
menu.drinkArray.forEach( (item) => { console.log(item);});
   ```
   {% hint style='info' %}
We can access properties inside objects using the `.` notation. The `drinkArray` property is available at object scope (meaning we can access the property as a part of the `menu` object), not global scope (meaning the entire script file cannot access the property).
   {% endhint %}

   {% hint style='working' %}
The entire object in the array is logged out. What if you want to only log the `label` within each drink? How would you change your log statement to do so?
   {% endhint %}

1. We'll have the `buildDrinkMenu()` iterate across the array and be responsible for building out the menu itself. Replace the call `menu.drinkArray.forEach` with `menu.buildDrinkMenu();`. You should see the log to the console say "inside buildDrinkMenu".


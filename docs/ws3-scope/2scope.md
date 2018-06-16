1. In Atom, open _my-script.js_ and navigate to the bottom of the file. Inside the `document.addEventListener("DOMContentLoaded", ...)` function, before the calls to register the event listeners for the order button, iterate over the `drinkArray` and log each element to the console using the following code
   ```javascript
menu.drinkArray.forEach( (item) => { console.log(item);});
   ```
   {% hint style='info' %}
We can access properties inside objects using the `.` notation. The `drinkArray` property is available at object scope, not global scope.
   {% endhint %}

   {% hint style='working' %}
The entire object in the array is logged out. What if you want to only log the `label` within each drink? How would you change your log statement to do so?
   {% endhint %}

1. We'll have the `buildDrinkMenu()` iterate across the array and be responsible for building out the menu itself. Replace the call `menu.drinkArray.forEach` with `menu.buildDrinkMenu();`. You should see the log to the console say "inside buildDrinkMenu".
   {% hint style='tip' %}
Defining responsibilities and grouping code for that purpose helps make code easier to maintain.
   {% endhint %}

1. Inside the `buildDrinkMenu` function, change the `console.log()` to log out `numberOfDrinks` using `console.log(numberOfDrinks);`. We can access a variable declared at global scope inside our function scope.
   {% hint style='tip' %}
The web app is broken right now so clicking the "Order" button has an error. We can't increment the `numberOfDrinks`. We will fix this as a bonus work.
   {% endhint %}

1. In the `buildDrinkMenu` function before the `console.log()`, declare a new variable called `numberOfDrinks` and set the value to 5. Notice the value logged.  
   {% hint style="info" %}
The `const` and `let` syntax has block scope, meaning it can't be accessed outside of the `buildDrinkMenu` function. In this case, tt creates a new variable with the same name but a different value and uses the new variable in place of the one declared at the global scope.

To help write maintainable code, use the most restrictive scope you can. Doing so will help prevent you from inadvertently changing a variable or unintentionally changing functionality. 
   {% endhint %}

1. Create a new function called `testLog` inside `buildDrinkMenu` after the `console.log()`. In the `testLog` function, log `numberOfDrinks` variable again. We can access variables declared in parent's scope from the child function. Your `buildDrinkMenu` function looks like this
   ```javascript
function () {
      const numberOfDrinks = 5;
      console.log(numberOfDrinks);

      function testLog() {
            console.log(numberOfDrinks);
      }

      testLog();
}
   ```
   {% hint style='tip' %}
This is an example of nested functions.
   {% endhint %}

1. Delete the `cocktails` array at the top of the _my-script.js_. 

1. You now have an error in the console because the code we wrote to iterate over `cocktails` no longer works. You should see "Uncaught ReferenceError: cocktails is not defined". We need to change how we're accessing the array. Find the `cocktails.forEach` at the bottom of _my-script.js_ file and replace with `menu.drinkArray.forEach`.
   {% hint style='info' %}
We couldn't access `label` directly before, so the same principle holds true for accessing `drinkArray` in the `menu` object. The `drinkArray` property is available at object scope, not global scope.
   {% endhint %}

1. We'll have the `buildDrinkMenu()` iterate across the array and be response for building out the menu itself. Replace the call `menu.drinkArray.forEach` with `menu.buildDrinkMenu();`. You should see the log to the console say "inside buildDrinkMenu".
   {% hint style='tip' %}
Defining responsibilities and grouping code for that purpose together helps make code easier to maintain.
   {% endhint %}

1. Inside the `buildDrinkMenu` function, change the `console.log()` to log out `numberOfDrinks` using `console.log(numberOfDrinks);`. We can access a variable declared at global scope inside our function scope.

1. In the `buildDrinkMenu` function before the `console.log()`, declare a new variable called `numberOfDrinks` and set the value to 5. Notice the value logged. 
   {% hint style="info" %}
The local scope wins over global scope.
   {% endhint %}

1. Create a new function called `testLog` inside `buildDrinkMenu` after the `console.log()`. In the `testLog` function log `numberOfDrinks` variable again. We can access variables declared in parent's scope from the child function. Your `buildDrinkMenu` function looks like this
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




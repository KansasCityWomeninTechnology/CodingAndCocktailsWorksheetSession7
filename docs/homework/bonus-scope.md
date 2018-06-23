# Explore Scope

Let's explore variable scope together to better understand how to access variables within a JavaScript application.

{% hint style='tip' %}
##### Hey Slacker!

Remember, we're here to help.
Join the KCWiT #codingandcocktails Slack Channel: [kcwit.slack.com](http://kcwit.slack.com)
{% endhint %}

1. Open Atom and start atom-live-server. Open Chrome DevTools in the browser tab that atom-live-server opens.
   {% hint style="tip" %}
Don't forget to save your file after each code change to see your web page reload. If another browser opens, you can open Chrome and open a tab using the same URL as the other browser tab.
   {% endhint %}

1. In _my-script.js_, add a new method called `testScope` to the `menu` object. Call the `testScope` method in the `document.addEventListener("DOMContentLoaded"...)` function. Follow the same pattern as what you did with `buildDrinkMenu` method.

1. Inside the `testScope` method, add a `console.log()` to log out `numberOfDrinks` and take a look at the console in Chrome. We can access a variable declared at global scope inside our function scope.

1. In the `testScope` function before the `console.log()`, declare a new variable called `numberOfDrinks` and set the value to 5. Notice the value logged.  
   {% hint style="info" %}
The `const` and `let` syntax has block scope, meaning it can't be accessed outside of the `testScope` function. In this case, it creates a new variable with the same name but a different value and uses the new variable in place of the one declared at the global scope.

To help write maintainable code, use the most restrictive scope you can. Doing so will help prevent you from inadvertently changing a variable or unintentionally changing functionality. 
   {% endhint %}

1. Create a new function called `inner` inside `testScope` after the `console.log()`. In the `inner` function, log `numberOfDrinks` variable again. We can access variables declared in parent's scope from the child function, so `inner` can access `testScope` variable. Your `testScope` function looks like this
   ```javascript
function () {
      const numberOfDrinks = 5;
      console.log(numberOfDrinks);

      function inner() {
            console.log(numberOfDrinks);
      }

      inner();
}
   ```
   {% hint style='tip' %}
This is an example of nested functions.
   {% endhint %}
   {% hint style='working' %}
What do you see in the console? What does `numberOfDrinks` log inside the `inner` function.
   {% endhint %}

1. Add a new `const` variable called `testVariable` inside `inner` function. You can make the value anything you want. How about "Hello there smartie pants!".

1. Outside the `inner` function (but still inside the `testScope`) function, try to log out your new `testVariable`. What do you see in the console?

1. What if you changed the `const` declaration to `let` or `var`? Can you log out your new `testVariable`?

1. What if you removed all declarations (no `const`, `let`, or `var`) to have `testVariable = "Hello there smartie pants!";`. What do you see in the console?
   {% hint style='working' %}
What scope is `testVariable` in if a parent function can access a variable declared inside a child function? (Hint- **global** scope).
   {% endhint %}


{% hint style='tip' %}
Feel free to explore more with scope variables and `this` by using console log. The more you practice, explore, and try things, the more you'll learn and understand. Mentors are happy to help via Slack!
{% endhint %}
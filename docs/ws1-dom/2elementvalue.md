1. Using Atom, open _my-script.js_ in the "assets/scripts" folder. Two functions are already defined in the file. Find the `onclick` event handler on line 4. Place your cursor between the opening and closing curly brace and press `Enter`. Your code should look like this
   ```javascript
document.getElementById('order-btn').onclick = function () {
};
   ```
   {% hint style='info' %}
The opening and closing curly brace signify the starting and ending boundaries for groups of code statements. All the code inside the curly brace are part of the same group. Code outside of the curly braces are not part of the group. In this case, all code inside the curly braces are part of a function and all code outside of the curly brace is not part of the function. You will see instructions to add code inside and outside functions tonights.
   {% endhint %}      

   {% hint style='tip' %}
View the worksheet and the IDE in split screen mode to make it easier to work through tonight's session. Check out the [helpful tips in the Setup guide](/setup#tips). 
   {% endhint %}

1. Add an alert with the message "Hi LadyDev!" inside the function to verify we wired up the click handler correctly. Save your file and click on the order button in Chrome. Do you see the alert pop up? Your click handler should look like this
   ```javascript
document.getElementById('order-btn').onclick = function () {
      alert("Hi LadyDev!");
};
   ```
   {% hint style='tip' %}
**Every time you make a change, save the file.** 

The atom-live-server package will automatically refresh the Chrome tab to keep the app up to date with your **saved** work. Atom alerts you to unsaved work by displaying a blue circle in the tab:

![](images/atom-save.png)

Save the file by navigating to **File** <i class="fa fa-long-arrow-right"></i> **Save** or by using the keyboard shortcut `cmd` + `s` for Macs and `ctrl` + `s` for Windows. Refer to [Helpful Keyboard Shortcuts](/references).
   {% endhint %}

1. Now that we know the click handler works, let's get the value of the form input for the name of the order. In Atom, add the following code inside the `onclick` function and remove the alert. Your click handler function should look like this
   ```javascript
document.getElementById('order-btn').onclick = function () {
      document.getElementById('order-form-input').value;
};
   ```

1. We want to see what the value of the input is. We can add another alert message, or we can log it out to the console. Let's use the console this time. Wrap the value of the form in the `console.log()` method by changing the code to look like this
   ```javascript
console.log(document.getElementById('order-form-input').value);
   ```

1. To see console logging in action, open the Chrome DevTools. Enter text in the name field and click on the order button. You should see your text write to the console. Leave DevTools open.

   {% hint style='tip' %}
Open Chrome DevTools by using `cmd` + `option` + `i` on Macs, `F12` on Windows, and `ctrl` + `shift` + `i` on Chromebooks. Refer to [Helpful Keyboard Shortcuts](/references).
   {% endhint %}   

1. Create a new function called 'submitOrder' that takes a parameter called 'name'. Back in Atom, place your cursor at the top of the _my-script.js_ file and press `Enter` a few times. Above the line of code containing `document.addEventListener...`, create the function by typing the following code
   ```javascript
const submitOrder = function (name) {};
   ```

1. The click handler function needs to call our new `submitOrder` function. Replace calling the `console.log()` with calling `submitOrder()` in the click handler function. The click handler function should look like this
   ```javascript
submitOrder(document.getElementById('order-form-input').value);
   ```
   {% hint style='info' %}
We are passing the value as a parameter to the `submitOrder` function. We can now access the value of the form input in the `submitOrder` function body using the variable `name`. 
   {% endhint %}   

1. To verify we wired it up correctly, let's alert on the `name` variable. Inside the `submitOrder` function, alert on `name`. Try testing this out in Chrome to see the alert pop up.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Change the <code>submitOrder</code> function to
<pre>
<code class="lang-javascript">
const submitOrder = function (name) {
      alert(name);
};
</code>
</pre>
</details>
   {% endhint %}

  {% hint style='tip' %}
Notice we can leave the name blank. The value will be empty but the alert still displays with nothing inside.  
  {% endhint %}   

1. Great! Now we can update the DOM with information about the order in the `submitOrder` function. We should also append extra text to their name so it sounds friendly. We can do this using **string concatenation**. In Atom, remove the alert message from the `submitOrder` function body and replace it with
   ```javascript
document.querySelector('.order-details').innerHTML = name + " would like a drink!";
   ```
  {% hint style='info' %}
We are using `document.querySelector` here instead of `document.getElementById`. We are querying for the class `order-details` instead of the element id. The `Document` API has different ways to find and access elements from the DOM depending on what you are trying to access and how many elements fit the criteria of the search. Check out the references for the section to read more about the different ways to access elements in the DOM. 
  {% endhint %}   

1. In Chrome, try adding your name and click the order button. Do you see your name added to the web page?
   {% hint style='tip' %}
You will use Atom to type code statements and Chrome to verify your work when your web page reloads. Don't forget to save _my-script.js_ every time you type a code statement.
   {% endhint %}



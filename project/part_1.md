# Part 1:  Review & Conditionals
#### Variables, Data Types, Functions, Comments, Mathematical Operators, Conditionals, Equality, and Concatenation

### First things first

#### <a href="https://kcwit.slack.com/messages/C0BGBKGG6/">Click here to open Slack</a>

If you have a tip that helped you with a step on the worksheet, you can easily share it with the group in Slack. Or if there are any issues with the worksheet [we make typos or there's an update to a tool that we didn't catch before the session], we may post updates in Slack. Plus, after class is over, Slack becomes a tool for you to gain access to mentors as you go through the homework, or any other questions that arise.

{% hint style='tip' %}
The answer key is linked at the end of this section if you’d like to reference it as you’re working.  Try your hardest to make an attempt and talk things over with a mentor before using it though!
{% endhint %}

{% hint style='danger' %}

If you're using a Chromebook, skip down to the Cloud9 instructions at the bottom.

{% endhint %}

### The Project

We will be adding interactivity to our Coding & Cocktails Drink Order App that some of you may have seen during our version control or jQuery sessions earlier this year. Not to worry if you didn't attend those sessions - this will be different functionality and practice!

### Setup

If you don't want Version Control practice or don't know what Version Control is, just start with step 1 below.

If you were at the Version Control session in April and would like to practice your Git skills, expand the section below and follow the steps.

<!--sec data-title="Version Control Practice" data-id="section0" data-show=true data-collapse=true ces-->
1. Sync your personal DrinkOrderApp fork with the KCWiT repository by following [GitHub's steps on syncing a fork](https://help.github.com/articles/syncing-a-fork/).
2. In iTerm2 or Git Bash type `git checkout programming-fundamentals-master` to switch to the appropriate branch.
3. Jump in on step 5 below.

Grab a mentor if you need some support as you do this!
<!--endsec-->

1. In Google Chrome, navigate to https://github.com/KansasCityWomeninTechnology/DrinkOrderApp/archive/programming-fundamentals-master.zip to download the project starting point.

2. Unzip the downloaded file and place the unzipped folder in your _CodingAndCocktails_ directory that was created during your tools setup.

3. Rename the folder from _DrinkOrderApp-programming-fundamentals-master_ to _DrinkOrderAppJS_.

4. In Atom, open the _DrinkOrderAppJS_ folder by opening the **File** menu and choosing **Add Project Folder**. Navigate to the unzipped _DrinkOrderAppJS_ folder and click OK.

5.  Open up the index.html file in Google Chrome to view the starting point.

  {% hint style='tip' %}
You can open the file in Google Chrome in a number of ways:

1. Open Google Chrome then choose **Open File...** from the **File** menu

2. Find the file in Finder (macs) or Windows Explorer (windows), right click on it and choose to open with Google Chrome.

3. Drag the file directly on to the Google Chrome browser window.

4. In GitBash, make sure you've changed directories into the one containing the file you want to open and type `start index.html`.

5. In iTerm2, make sure you've changed directories into the one containing the file you want to open and type `open index.html`.
  {% endhint %}

### Submit an Order

###### Create the function
First we'll add a function to handle drink orders. 
  
  1. In Atom, in the _assets/scripts_ folder, find the _my-scripts.js_ file and double click on it to open. 
  
  2. Find the submitOrder function comment:
```
/**
 * submitOrder Function
 * 
 * Increment orderCount, gather and display order details.
 * The code from the Worksheet Part 1: Submit an Order, Step 2 should go on the line just below the comment close.
 */
 ```
 
  3. On the line just below the closing `*/`, create a variable set equal to a function by typing out this:

    `var submitOrder = function () {};`

###### Gather User Input
Next, we need to gather some input from the user and save it off into additional variables.

  {% hint style='info' %}
We’ll be using jQuery (a JavaScript library, or, set of functions to help in application development) to help simplify some of the coding but we’ll supply that portion of the code for you.  Instead of copying and pasting from this worksheet, try typing out what you see.
  {% endhint %}

  1. Place your cursor in between the curly braces from step 3 and press enter.  The cursor should now be inside the function body. 
  
  2. Type `var orderName = $("#order-form-input").val();`.

  {% hint style='info' %}
This code is finding the HTML element that has the id "order-form-input" (the input box you can see on the page) and grabbing the value that has been entered there.

Missed the HTML session and have no clue what an element is? Grab a mentor to talk through what HTML is!
  {% endhint %}

###### View Application Data
Now that the input data is saved into a variable, make sure we got a value and try viewing data via a console.log statement. 

  1. In the same function body as before, on the line underneath the orderName variable, type `console.log(orderName);`.

###### Call the function
In order to see what we’ve accomplished so far, the function has to be run.  

  1. In the _my-scripts.js_ file, find the comment that says `// call submitOrder function when order button is clicked (Worksheet Part 1: Call the Function, Step 1)` around line 28.  Place your cursor at the end of that line and press enter.  
  
  2. On that new line, type `submitOrder();` to call the submitOrder function. 

  {% hint style='tip' %}
Inside the parentheses is where you would pass parameters to the function but since ours does not require parameters, we just leave them empty.
  {% endhint %}

  3. Save your _my-scripts.js_ file.
  
  4. In Google Chrome, reload your page and open up the console by pushing the F12 button on a windows machine or `cmd+opt+i` buttons on a mac.

  5. Enter your name in the input box and push the Order button.  

  6. Your name should appear in the Google Chrome console!  Check your function name or grab a mentor if it is not showing up!


###### Ordering Drinks
We also want to save the drink name to display it with the order. 

 1. Add a new line after the `console.log();` line.
 
 2. Type `var drinkName = $("input[type='radio']:checked").val();` to save the selected drink to a variable called drinkName.

  {% hint style='info' %}
The code in step 2 here is looking for the value of the checked radio button input.  It is storing that data in a variable called `drinkName`.
  {% endhint %}

###### Display Orders
Finally we want to display the orders that are coming in! 

  1. Add a new line after the `var drinkName ...` line.
  
  2. Type `$("#order-details").append("<h1>" + <your code goes here> + "</h1>");` 

  {% hint style='danger' %}
Replace the `<your code goes here>` portion to display the message "Jane would like a Strong Lady".  You'll need to use concatenation to build that string using your variables `orderName`, `drinkName` and a string `" would like a "`.

**If you’re struggling here, grab a mentor to talk through concatenation!**
  {% endhint %}

  {% hint style='info' %}
The code in step 2 is finding the HTML element with the id of order-details and appending to (or placing inside of) that element a new h1 (header 1) element with the text that we specify using the append method.
  {% endhint %}

  {% hint style='info' %}
These orders are only based on what is being submitted on your device in your current (Google Chrome) browser session. Since we don’t have a server connected, the data is only persisted as long as you don’t refresh the page in your browser. Once you hit refresh, the variables and page content are reset - starting over.  In order to clear out your order details, just refresh your browser window.
  {% endhint %}

  3. In Atom, save your _my-scripts.js_ file
  
  4. In Google Chrome, reload the page.  You should now be able to select a drink, enter your name, hit the order button and have your order text display in the light purple order detail area on your webpage!

**You’ve added drink ordering to your website! Sounds like it’s time to grab one of your own!**
  
### Count Orders
We’ll want to make sure we don’t overwhelm our bartender with 50 drink orders at one time so let’s make sure to count how many drinks have been ordered.  

  1. In Atom, in the _my-scripts.js_ file, find the comment `// Initialize orderCount variable to 0 (Worksheet Part 1: Count Orders, Step 1)` at the very top of the file.  Place your cursor at the end of that comment and press enter to add a new line just below the comment.  
  
  2. On that new line, create a variable named `orderCount` and initialize it to 0.  Initializing is setting the starting value of a variable, the value to the right of the `=`.

  3. As the first line inside the body (Remember - that means inside those curly braces!) of the `submitOrder` function, type `orderCount++` to add one to the orderCount variable each time an order is placed.  

  {% hint style='tip' %}
`++` is a common shortcut for adding one in programming! 
  {% endhint %}

  4. In Atom, in the _my-scripts.js_ file, find the comment for the `updateOrderCount` function: 
```
/**
* updateOrderCount Function
*
* Displays number of drinks currently in the order queue.
* @param {number} count - counter for orders
* The code from the Worksheet Part 1: Count Orders, Step 4 should go on the line just below the comment close.
*/
```

  5. On the line right below the closing `*/` for that comment, add a new function to your file named `updateOrderCount`. Pass a parameter to this function called `count`.  

  {% hint style='tip' %}
Remember to pass a parameter that you add it inside the parenthesis like this:`var myFunctionName = function (myParameterName) { }`
  {% endhint %}

  6. Inside the body of the `updateOrderCount` function type: `$('#drink-count').html("Drinks Ordered: " + count);`

  {% hint style='info' %}
This code is finding the HTML element with the id of `drink-count` and changing the content of that HTML element to be what we pass to the jQuery html method - in this case, the string “Drinks Ordered:” and our updated order count.
  {% endhint %}

  7. This function needs to be called inside the body of the `submitOrder` function, on a new line directly below the following code: `$("#order-details").append("<h1>" + orderName + " would like a " + drinkName + "</h1>");`

  {% hint style='info' %} 
Remember how we call functions like in Step 2 under the "Call the Function" section above? This time you’ll need to pass the `orderCount` variable to the `updateOrderCount` function! `myFunction(passedParameter);`
  {% endhint %}

###### Alerts & Conditionals
Take a minute to read about alert boxes here: [bit.ly/CnCAlert](http://bit.ly/CnCAlert). We’ll utilize one in our next step. You can customize the message to display whatever you want.

You will make the following changes in Atom, in the _my-scripts.js_ file. The placement of this is a little tricky as we need to wrap the conditional around some existing code.  

  1. Place the cursor at the end of the `var drinkName ...` line and press enter.  On that new line, type out your `if (condition) {` code where the condition is if the `orderCount` is less than or equal to 5.  

  {% hint style='tip' %} 
[View documentation on the if statement on the Mozilla Developer Network pages.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
  {% endhint %}
  
  2. Indent the line directly below it (`$("#order-details").append("<h1>" + orderName + " would like a " + drinkName + "</h1>");`) so it is nested inside the body of the if statement. This will add the order to the display if there is still room for orders
  
  3. Make sure your if statement body is closed out with a closing curly brace after the nested code.
   
  4. Next to that closing curly brace, add an `else` clause to the if statement.  
  
  5. In the body of the else, display an alert that says “Drink order queue is full.  Please try ordering again in a few minutes.” 

  {% hint style='info' %} 
These orders are only based on what is being submitted on your device in the current browser session.  Since we don’t have a server connected, the data is only persisted as long as you don’t refresh your browser. Once you run a refresh the variables and page content are reset starting over so in order to reset your order count, just refresh your browser window!
  {% endhint %}

  6. In Atom, save your _my-scripts.js_ file.

  7. In Google Chrome, reload your page, try adding 6 orders and see your alert pop up!

  8.  Check your work with our answer key here: [bit.ly/CnCPFKey1](http://bit.ly/CnCPFKey1)

**You’ve finished part one! Celebrate with a toast with your neighbor!**

<!--sec data-title="Chromebooks Only: Cloud9 Instructions" data-id="section1" data-show=true data-collapse=true ces-->

1. Sign up for an account at [c9.io](https://c9.io)

   Note: It will ask you for credit card information, but you will not get charged for anything since we do not use features of Cloud9 that cost money. Ask a mentor for the Coding & Cocktails card for Cloud9.

2. Confirm your account from your email and log in to Cloud9.

3. Select **Workspaces** from the left side panel if you are not already there.

4. Choose **Create a new workspace**.

5. Add a name for your workspace - it can be anything you like. You do not need a description, but feel free to add one if you like.

6. Leave your workspace as **Public**.

7. Clone the repo from Github so the files we need for Part I will be in our workspace for us.

  1. In the **Clone from Git or Mercurial URL** field enter `https://github.com/KansasCityWomeninTechnology/DrinkOrderApp.git`

8. In the template section leave the template as  **HTML5**.

9. Click on the **Create Workspace** button.

   Cloud9 will take a minute and create your workspace here.

10. All the files that were cloned from the Github repo are in your workspace. 

11. Close the open _README.md_ tab by clicking on the x on the tab.

12. Open the _index.html_ file in the editor by double clicking on the file name on the left.

13. In the console at the bottom of the workspace type `git checkout programming-fundamentals-master` to switch to the starting point of the project.

13. On the top menu bar click on **Preview** and choose **Live Preview File** to open the preview in your workspace.  You may enlarge it to another Google Chrome tab by clicking on the expand icon.

    ![](/images/expand.png)

Now you're ready to start with the **Submit an Order > Create a Function** section above!

<!--endsec-->

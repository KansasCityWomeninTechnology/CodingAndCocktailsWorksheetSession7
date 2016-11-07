### Part 1:  Variables, Data Types, Functions, Comments, Console, Mathematical Operators, Conditionals, Equality, Addition and Concatenation {#part-1-variables-data-types-functions-comments-console-mathematical-operators-conditionals-equality-addition-and-concatenation}

Note: The answer key is linked in step 11 if you’d like to reference it as you’re working.  Try your hardest to make an attempt and talk things over with a mentor before using it though!

1.  First we need to get to our starting point utilizing git and our GitHub accounts.

  1.  If you’ve never been to Coding &amp; Cocktails before follow these steps:

      1.  In google chrome using your GitHub account, fork the DrinkOrderApp repository ([bit.ly/CnCPFStrt](https://www.google.com/url?q=http://bit.ly/CnCPFStrt&sa=D&ust=1478494043497000&usg=AFQjCNEYyldhAY1JFnH-TdLkjf6afHH4rw)) to your own account by pressing the Fork button (                                                   ) in the upper right.<br>     ![Capture.PNG](/images/image00.png)

      1.  On the GitHub site in Google Chrome, grab the https URL from GitHub (click on the clipboard icon on the right side to copy the URL):<br>

        ![Capture.PNG](/images/image01.png)

      1.  In your command line tool (Git Bash on windows and iTerm2 on macs), change directory into the **CodingAndCocktails** directory you created during the prep work if you’re not there yet: `cd CodingAndCocktails`

      1.  Still in the command line tool run the following command to clone the repository to your local device: `git clone <paste URL copied from GitHub above>` (Hint: use shift + enter on Windows) do not include angle brackets`

      1.  Finally, checkout the branch we will use as our starting point for this evening with the following command in the command line tool: `git checkout programming-fundamentals-master`

  1.  If you’ve been to Coding &amp; Cocktails previously and worked in the DrinkOrderApp repository follow these steps in your command line tool (Git Bash on windows or iTerm2 on macs) to get to the right starting point:

      1.  Make sure you’ve navigated into the DrinkOrderApp directory in your command line tool. (Hint: cd is the command for “change directory”)

      1.  Add your upstream remote (the repository that you forked) by running the following command:  `git remote add upstream https://github.com/KansasCityWomeninTechnology/DrinkOrderApp.git`

      1.  Fetch any upstream changes or new branches that have been made since you last worked in the repository: `git fetch upstream`

      1.  Checkout your new branch to start from: `git checkout programming-fundamentals-master`

1.  Open up the index.html file in Google Chrome to view our starting point.

1.  First we need to add a function that will handle our orders. We will make these changes  to the end of  the **my-scripts.js** file in Sublime Text. Open your text editor and open the folder for the Drink order app.  Find the **my-scripts.js** file and open it. In order to give our function a name create a variable set equal to the function like this:

    `var submitOrder = function () {}`

1.  Next, let’s get some more practice using variables.  We’ll  gather some input from the user and save it off.

  Note: we’ll be using some jQuery (a JavaScript library) to help simplify some of the coding but we’ll supply that portion of the code for you.  Instead of copying and pasting from this document try typing out what you see.

  1.  Create a variable called `orderName` inside the `submitOrder` function.  Remember to start with the `var` keyword! Your function code goes inside the function’s curly braces - remember the parentheses are where we could pass parameters to the function but we won’t need those for our project.

   1.  Set the variable’s value to the following: `$("#order-form-input").val()`; 

      This code is finding the HTML element that has the id order-form-input (which is our input box on the page) and grabbing the value that has been entered there.

1.  Now that you’ve saved that string into a variable, let’s make sure we get a value and try our console.log statements!

  1.  On the line underneath your variable add a `console.log();` statement, placing your variable name inside the parentheses.

  1.  In order to see what we’ve accomplished so far the function has to be called.  Inside the click event handler for the order button add a call to the “submitOrder” function.  To call a function write the name of the function followed by open and close parentheses.  Inside the parentheses is where you would pass parameters to the function but since ours does not require parameters we just leave them empty. Example:myFunction();

    1.  Save your work, reload your page in Google Chrome and open up the developer tools or console (push F12 on a windows machine or cmd+opt+i on a mac)

    1.  Enter your name in the input box and push the Order button.  

    1.  Your name should appear in the Google Chrome console!  Check your function name or grab a mentor if it is not showing up!

1.  We also want to save off the drink name to display it with the order so add this code to your submitOrder function after your orderName variable (but still inside the function’s curly braces!):

        var drinkName = $("input[type="radio"]:checked").val();

       This code is looking for the value of the checked radio input.  It is storing that text in a variable called `drinkName`.  

1.  Finally we want to display the orders that are coming in! Add this code snippet to your function after both variables.  Try concatenating your variables and a string together replacing the &lt;your code goes here&gt; (including the angle brackets) with your string concatenation.  Try to make the message say what would come out as “Jane would like a Strong Lady”. Keep in mind your name is saved in the `orderName` variable and the drink name is saved in the `drinkName` variable.

  If you’re struggling grab a mentor or take a peek at the answer key here: [bit.ly/CnC1stKey](https://www.google.com/url?q=http://bit.ly/CnC1stKey&sa=D&ust=1478494043517000&usg=AFQjCNH_ciqas6E-dHypgorOqxTz9ponUQ) (note: The answer key will look slightly different than what your code should look like at this point since it is the answer key for the entire part 1, not just until this point so grab a mentor if you’re confused!)

        $("#order-details").append("<h1>" + <your code goes here> + "</h1>");

    This code is finding the HTML element with the id of order-details and appending to (or placing inside of) that element a new h1 element with the text that we specify using the append method.

  *Note: These orders are only based on what is being submitted on your device in your current browser session. Since we don’t have a server connected in, the data is only persisted as long as you don’t refresh your browser. Once you run a refresh, the variables and page content are reset starting over.  In order to clear out your order details, just refresh your browser window.
*
1.  Save your file, go to your chrome browser and reload the page.  You should now be able to select a drink, enter your name, hit the order button and have your order text display in the light purple order detail area on your webpage!

  **You’ve added drink ordering to your website! Sounds like it’s time to grab another!
**
1.  We’ll want to make sure we don’t overwhelm our bartender with 50 drink orders at one time so let’s make sure to count how many drinks have been ordered.  

  1.  Back in **my-scripts.js** in Sublime Text add an `orderCount` variable to the top of your file and initialize it to 0\.  Initializing is setting the starting value of a variable.

  1.  Inside the `submitOrder` function make sure to add one to the `orderCount` variable so it gets incremented each time we create another order. Remember there’s a shortcut for adding one in programming! 

  1.  This time we’re going to add a function that has a parameter passed to it.  Add a new function to your file called `updateOrderCount`.  Make sure you pass a parameter to this function called `count`.  Remember to pass a parameter that you add it inside the parenthesis like this:<br> `var myFunction = function (myParameter) { }`

  1.  Inside the updateOrderCount function add this code: `$('#drink-count').html("Drinks Ordered: " + count);`

      This code is finding the HTML element with the id of `drink-count` and changing the content of that HTML element to be what we pass to the html method, here the string “Drinks Ordered:” and our updated order count.

  1.  You’ll need to add a call to this function inside the submitOrder function ( this should go just under the code to add the order display.)  *Remember how we call functions like in step 5b above but this time you’ll need to pass the orderCount variable to the function!*

            myFunction(passedParameter);

   1.  Take a minute to read about alert boxes.  We’ll utilize one in our next step.  You can find information about alert boxes here: [bit.ly/CnCAlert](https://www.google.com/url?q=http://bit.ly/CnCAlert&sa=D&ust=1478494043527000&usg=AFQjCNF1XotRJyoxlDrutZAu4zHyBHNVnw). You can customize the message they display to say whatever you want.

  1.  Add a conditional to check if the `orderCount` is greater than 5\.  If so display an alert that says “Drink order queue is full.  Please try ordering again in a few minutes.” Otherwise (else) add the order to the display! Check this out if you need a reminder on what if statements look like: [bit.ly/CnCIfElse](https://www.google.com/url?q=http://bit.ly/CnCIfElse&sa=D&ust=1478494043529000&usg=AFQjCNGczjKQidYybYcx-YdZ-dk61FeX9w)

           *Note: These orders are only based on what is being submitted on your device in the current browser session.  Since we don’t have a server connected in, the data is only persisted as long as you don’t refresh your browser. Once you run a refresh the variables and page content are reset starting over so in order to reset your order count, just refresh your browser window!*

1.  Save your file, reload your page in chrome, try adding 6 orders and see your alert!

1.  Check your work with our answer key here: [bit.ly/CnC1stKey](https://www.google.com/url?q=http://bit.ly/CnC1stKey&sa=D&ust=1478494043531000&usg=AFQjCNEvCWXEvBIxVNuzUcFa5qTIOBCIfw)

**You’ve finished part one! Celebrate with a toast with your neighbor!**
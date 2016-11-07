## Bonus Section {#bonus-section}

If you’ve made it through all of the above or want to practice a little further at home, try ordering a drink without entering a name.  That’s not useful, is it? This is called a bug which is something you’ll run into regularly as a developer. Let’s fix that with another conditional!  These changes need to happen in my-scripts.js in Sublime Text.

1.  Check to see if `orderName` has a value.  We just want the conditional to evaluate to true and an undefined value will always evaluate to the boolean value false. That means all we have to do to check whether or not `orderName` has a value is check `if (orderName)`

1.  Wrap that if statement around the if statement that is checking our drink count.  This is called nesting our if statements.  It is bad practice to nest too many if statements since it decreases code readability which makes maintenance more difficult.  It can also increase the potential for a bug or defect in your code since keeping track of what if branch you are in is hard when you get too many nested levels.

1.  Trigger an alert that happens if the `orderName` does not have a value.  Make it say something like “Oops! Please enter your name to order your drink.”

1.  Save your changes and refresh the page in Google Chrome.  Try placing an order without a name now and see what happens!

1.  Compare with the bonus answer key here: [bit.ly/CnCPFBonusKey](https://www.google.com/url?q=http://bit.ly/CnCPFBonusKey&sa=D&ust=1478494043556000&usg=AFQjCNH6gzVyFdOfkbCSdNMYWHncO93dfg)
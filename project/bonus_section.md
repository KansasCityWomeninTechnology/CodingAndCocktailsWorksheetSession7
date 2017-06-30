## Bonus!

If you’ve made it through all of the above or want to practice a little further at home, try ordering a drink without entering a name.  

That’s not useful, is it? This is called a bug which is something you’ll run into regularly as a developer. Let’s fix that with another conditional!  These changes need to happen in _my-scripts.js_ in Atom.

1.  First, check to see if `orderName` has a value.  We just want the conditional to evaluate to true and an undefined value will always evaluate to the boolean value false. That means all we have to do to check whether or not `orderName` has a value is check `if (orderName) {`

2.  Wrap that if statement around the if statement that is checking our drink count.  This is called "nesting" if statements.  

    {% hint style='info' %}
It is bad practice to nest too many if statements since it decreases code readability which in turn makes maintenance more difficult.  It can also increase the potential for a bug or defect in your code since keeping track of what if branch you are in can be difficult when you get too many nested levels.
    {% endhint %}

3.  Trigger an alert if the `orderName` does not have a value.  It should say something like “Oops! Please enter your name to order your drink.”

4.  Save your changes and refresh the page in Google Chrome.  Try placing an order without a name now and see what happens!

5.  Compare with the bonus answer key here: [bit.ly/CnCPFBonusKey](http://bit.ly/CnCPFBonusKey)
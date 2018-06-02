1. Change console.log(drinkList) to console.log(this.drinkList) (add some more console.log of this maybe of the event??)

1. Inside the `buildDrinkList` function, add a forEach for the drinkList and write out to console
```javascript
 this.drinkList.forEach( (drink)=> {
     console.log(drink);
 });
 ```
    * Add hint about `this` and arrow functions. 

1. We're back! let's start building a DOM for the drink list

1. Inside the `forEach` create the label element setting className to 'radio' and use the drink.id (This is the parent)
```javascript
let labelNode = document.createElement("label");
  labelNode.className = "radio";
  labelNode.setAttribute("for", menuItem.id);
```

1. Create the input element and use the drink.label as the value
```javascript
let radioNode = document.createElement("input")
  radioNode.id = menuItem.id;
  radioNode.name = "drink";
  radioNode.setAttribute("type", "radio");
  radioNode.setAttribute("value", menuItem.label);
```

1. Create the text for the label
```javascript
  var textNode = document.createTextNode(menuItem.label);
```

1. Add the input and text to the label 
```javascript
labelNode.appendChild(radioNode);
labelNode.appendChild(textNode);
```

1. We can build up a separate DOM and add it to our main DOM tree when complete to result in better performance using a DocumentFragment. Before the `forEach` create a new fragment `let fragment = document.createDocumentFragment();`

1. As the very last line inside the `forEach` add `fragment.appendChild(labelNode)` to add the label to the fragment DOM.

1. Outside the `forEach` as the last line inside the `buildDrinkList` function add `document.querySelector('.radio-group').appendChild(fragment);`

    * Why go through this effort? Add a new drink to show why easier than putting in html.


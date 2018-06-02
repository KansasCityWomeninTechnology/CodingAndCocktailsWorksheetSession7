1. Create submitOrder function
  * Hint on difference on function declaration and function expression?

1. `document.getElementById('order-form-input').value`. Console log it

1. Pass value into submitOrder and show alert.
   * Hint on always showing message even if input is blank

1. Remove console.log

1. update submitOrder
```javascript
const submitOrder = function ( name ) {
    document.querySelector('.order-details').innerHTML = name + " would like a drink!";
};
```

* Hint on difference on getElementById and querySelector?


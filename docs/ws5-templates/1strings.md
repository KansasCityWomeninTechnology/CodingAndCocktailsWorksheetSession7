1. In `updateOrderCount` function, update innerHTML to use template literal by changing text to
```javascript
`Drinks Ordered: ${count};`
```

1. Also try adding an expression? `Drinks Ordered: ${count + 10}`?

1. Try changing the string concatenation in `submitOrder` method
    * help text
    ```javascript
    let textNode = document.createTextNode(`${name} would like a ${drink}`);
    ```

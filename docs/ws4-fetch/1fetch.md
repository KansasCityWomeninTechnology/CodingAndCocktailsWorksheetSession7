1. Declare a new function called `fetchImage` in the global scope after the `updateOrderCount` function.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Add <code>const fetchImage = () => {}; </code> after the <code>updateOrderCount</code> function.
</details>
   {% endhint %}

1. Inside the `if` statement in `submitOrder` function, add a call to `fetchImage();` before create the node.

1. Inside the `fetchImage` function, declare a new `const` variable called `url`. Assign the value to 'https://source.unsplash.com/collection/2187331/300x200'.
   ```javascript
const fetchImage = () => {
    const url = 'https://source.unsplash.com/collection/2187331';
};
   ```
1. Call `fetch` with the `url` as a parameter.
   {% hint style='working' %}
<details>
<summary>
Need a little help? Expand this section for guidance. 
</summary> 
Add <code>fetch(url);</code> after the <code>url</code> declaration in the function.
</details>
   {% endhint %}

1. In DevTools, open the **Network** tab. Press ![](images/clear-requests.png) **Clear** button to clear out any existing network requests. Place a drink order and click the order button. You'll see network requests made. Click on the line that has the word "photo". You see tabs for **Headers**, **Preview**, **Response**, and **Timing**. You can click on those tabs to see different information about the request.

1. Let's add in the remaining code we need to use `fetch()`. Back in _my-script.js_ replace the exiting `fetch(url);` call with the following code with console logging built in.
   ```javascript
fetch(url)
      .then((response) => { return response.blob(); })
      .then((blob) => {
            console.log(blob);
       })
       .catch( (error) => { console.log(error); });
   ```

1. In Chrome, add a drink order and take a look at the console. Do you see a `Blob` object? Feel free to inspect the object.

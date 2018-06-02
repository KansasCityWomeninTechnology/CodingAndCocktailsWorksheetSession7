1. Create a new function named `fetchImage` with a parameter called `imageId`. You can declare it anywhere in the global scope 
```javascript
const fetchImage = (imageId) => {

};
```

1. Inside the `submitOrder` methods `if` clause, call `fetchImage('')` 

1. Define a variable inside the `fetchImage` function called url and set it to 'https://source.unsplash.com/collection/2187331'
`const url = 'https://source.unsplash.com/collection/2187331';`

1. Call `fetch` with the url as a parameter.

1. Open the network tab in Chrome DevTools. Click the clear button and place a drink order. Notice we make a network call out to the URL.

1. The `fetch` api returns a **Promise**. We need to format the response first before we can use it Change the call to `fetch` to look like this
```javascript
    fetch(url)
        .then((response) => { return response.blob(); })
        .then((blob) => {
            console.log(blob);
        })
        .catch( (error) => { console.log(error); });
```


1. Inspect the console and see what is returned from the API
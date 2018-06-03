1. Inside callback for `fetch`, below the `console.log(data);`, add the following code to connect the image url.
   ```javascript
const imgUrl = URL.createObjectURL(blob);
document.getElementById('cocktail-image').src= imgUrl;
   ```
1. Inside callback for fetch, below the `console.log(data);`, add 
```javascript
const imgUrl = URL.createObjectURL(blob);
document.getElementById('cocktail-image').src= imgUrl;
```
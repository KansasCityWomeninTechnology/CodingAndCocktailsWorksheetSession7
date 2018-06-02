1. create header node
    `let node = document.createElement('h3');`

    * 

1. create text node
    `    let textNode = document.createTextNode(name + " would like a " + drink);`

1. append text node to the h1 element node
 `    node.appendChild(textNode); `

1. append node to element
`    document.querySelector('.order-details').appendChild(node);`

1. Inspect in Chrome DevTools elements view??
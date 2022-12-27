# Learn JavaScript

## Arrow Function

There are so many ways to create a function: 


```js

//************* Variable 
// Define
const ehsanFunction = function(value) {
    return value * 2
}

// Call
- ehsanFunction(2)

//************* function

// Define
function ehsanFunction(value) {
    return value * 2
}

// Call
ehsanFunction(2)

//************* Arrow function
// Define
ehsanFunction = (value) => {
    return value * 2
}
// Same as above ^^^
ehsanFunction = (value) => value * 2

// Call 
ehsanFunction(2)

// IFEE (Immediately Function Invoke )

// Define and Call
(function ehsanFunction(value) {
    return value * 2
})()


```

## Call Back
Instead of assign a variable and call in next few lines, we can do both in one line. 

```js 
// Select a p1 tag
const pTagSelector = cy.get(".p1")
// check of the tag has something
pTagSelector.contains("Jeff Shomali")

// Same as above two lines ^^^
cy.get(".p1").then(pTagSelector => {
    pTagSelector.contains("Jeff Shomali")
})
```



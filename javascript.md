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


// Anonymous Function 

const value = () => fetch('thisurl.com/getNumber') // 2
ehsanFunction(() ) // 4





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


```js 


class cy {
  const get = (value) => {
      return document.getElementById(value)
  }

}


EhsanById("p1Tag")

$("p1Tag")

cy.get("p1Tag")



```

## Javascript Secret Keywords 

Operators

```js 
- Anything behind the equal sign is variable            here = 
- Anything before start parabthesis is function         here ( )
- Anything between brackets are logic                   { here }
- Anything between Parenthesis is parameters/pass       (p1, p2 )

// Define
const 💫 = (value) => cy.get(value)

// Call
💫()

// Define a class contains a function
class ehsan {
    const 💫 = (value) => cy.get(value)
}

// Call
ehsan.💫()

```


### Things to learn in JavaScript

- Create a flash card for qll below concepts in Cheqq.com/flashcrads
1. Arrow Function 
2. Ways to create a function 
3. Anonymous Function 


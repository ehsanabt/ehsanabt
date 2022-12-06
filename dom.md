- [Learn DOM manipulation](#learn-dom-manipulation)
  - [What is DOM?](#what-is-dom)
  - [Why as a QA Engnieer we need DOM](#why-as-a-qa-engnieer-we-need-dom)
  - [All Javascript DOM functions](#all-javascript-dom-functions)
      - [getElementById](#getelementbyid)
      - [getElementByClassName](#getelementbyclassname)
      - [querySelector](#queryselector)
      - [We can have access to children of a parent by:](#we-can-have-access-to-children-of-a-parent-by)
      - [We can have access to parent from child:](#we-can-have-access-to-parent-from-child)
      - [Select sibilings:](#select-sibilings)
      - [Move Forward and Backward from an element](#move-forward-and-backward-from-an-element)
  - [We can change the content of an element by using `innerHTML`](#we-can-change-the-content-of-an-element-by-using-innerhtml)
  - [Other ways of changing HTML elements:](#other-ways-of-changing-html-elements)
  - [Changing style of a HTML element](#changing-style-of-a-html-element)
  - [Event listener](#event-listener)
  - [We can make an element and APPEND it in the middle of our code:](#we-can-make-an-element-and-append-it-in-the-middle-of-our-code)
      - [Code description;](#code-description)


# Learn DOM manipulation


## What is DOM?

It is a programming interface that allows us to create, change, or remove elements from the HTML document. We can also add events to these elements to make our page more dynamic.

The DOM views an HTML document as a tree of nodes. A node represents an HTML element.

## Why as a QA Engnieer we need DOM

We can get data from elements of a page to check if they are correct or not, and if they are not correct we can show a message on the screen or change the color of that element...


## All Javascript DOM functions

#### getElementById
`document.getElementById("ID-Name")`


#### getElementByClassName
`document.getElementByClassName("ClassName")`


#### querySelector
`document.querySelector("Use CSS Selector for exmaple: #ID-Name")`

`document.querySelector(".Class-Name")`

* querySelector only selects the first element, if you want to select all the elements:

`document.querySelectorAll(.class_Name)`

#### We can have access to children of a parent by:

`const grandParents = document.querySelector(".grandParent")`

`const parent = Array.form(grandparent.
children)`

`const parentOne = parent[0]`

`const children = parentOne.children`

#### We can have access to parent from child:

`const childOne = document.quesryselector("#childOne")`

`const parent = childOne.parent`

#### Select sibilings:

`const childOne = document.querySelector(#childone)`

`const childTwo = childOne.nextElementSibiling`

#### Move Forward and Backward from an element

`childTwo.previousElementSibiling`

## We can change the content of an element by using `innerHTML`

`document.getElementById ("demo").innerHtml = "Hello"`

## Other ways of changing HTML elements:

| Syntax | Descriptiom
|--------|------------|
|`element.attribute = new Value`| Change the attribute value of an element|
|`element.style.property= new style`| Change the style of a HTML file|


## Changing style of a HTML element

`document.getElementsByID("ID").style.color = "blue";`

## Event listener

`document.getElementsById("ID").addEventListener("click",Function);`

## We can make an element and APPEND it in the middle of our code:

`<div id="div1">`

  `<p id="p1">This is a paragraph.</p>`

  `<p id="p2">This is another paragraph.</p>`

`</div>`

`<script>`


`const para = document.createElement("p");`


`const node = document.createTextNode("This is new.");`


`para.appendChild(node);`

`const element = document.getElementById("div1");`


`element.appendChild(para);`

`</script>`

#### Code description;

`This code creates a new <p> element:`

`const para = document.createElement("p");`

To add text to the `<p>` element, you must create a text node first. This code creates a text node:

`const node = document.createTextNode("This is a new paragraph.");`

Then you must append the text node to the `<p>` element:

`para.appendChild(node);`

Finally you must append the new element to an existing element.

This code finds an existing element:

`const element = document.getElementById("div1");`

This code appends the new element to the existing element:

`element.appendChild(para);`

- ### Read W3School full article: 
  (https://www.w3schools.com/js/js_htmldom.asp)


**Why?**

**When should we use this?**
## Command for start testing:

 `$ npx cypress open`

 `$ ./node_modules/.bin/cypress open`

 ## Command for start testing without opening browser:

 `$ ./node_modules/.bin/cypress run`

## Check cypress documentation for having more commands:

[https://docs.cypress.io/guides/guides/command-line](https://docs.cypress.io/guides/guides/command-line)

 ## Command for updating cypress to the specific version:

```bash 

$ npm install --save-dev cypress@11.2.0

# Same as above ^^^
$ npm install -D cypress@11.2.0

```
 ## Cypress documentation

 Use the following website: [https://docs.cypress.io/](https://docs.cypress.io/)


 ## Mocha

 Mocha is a feature-rich JavaScript test framework running on Node.js and in the browser, making asynchronous testing simple and fun. Mocha tests run serially, allowing for flexible and accurate reporting, while mapping uncaught exceptions to the correct test cases.

 mostly 2 functions are used in Moca:
 
 `describe()` & `it()`  

#### describe() 
is a simple way to group our test in Moca, Basically enabling us to group a series of tests together.

#### it()
is a way to describe each individual test case that are inside of a describe block.

`describe()` is used to define and group tests.

`it()` is used to define individual test cases. 


### * We need to type following code in the beginning of the cypress code to access cypress command library:

`$ /// <reference types="Cypress" />`


## Chrome add-on for CSS selectors

#### Ranorex Selocity

You can select a tag with it and then specify it with selecting one of its child via using following syntax: `li > a` or `button[type="submit"]` then Ranorex Selocity will show us the number of selected items, so we can change the syntax to have only 1 selected item!

## Xpath selectors

[W3school.com Xpath syntax](https://www.w3schools.com/xml/xpath_syntax.asp)

## Installing Xpath package on Visual studio

npm install -D cypress-xpath

#### You have to add this peace of code to e2e.js file in support folder:

'require('cypress-xpath')'

#### You have to add this peace of code on the top of your test code:

`/// reference types="cypress-xpath" />`


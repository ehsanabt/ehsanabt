For being ready to write a test we have to follow below steps:

1- Create a folder

2- Open the folder in VS code

3- Open Terminal

4- Put it on bash

5- Run command: npm init

6- Enter below information:

version: (1.0.0) 
description: CNN Automation Test
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: Ehsan Abtahi

7- Run command: npm install --save-dev cypress@12.6.0

8- Run command: npm i npx

9- Run command: npx cypress open

10- Open cypress.config.js and add below line:

specPattern: "cypress/e2e/**/*.js"

so our cypress.config.js would be like below:

```js 
const { defineConfig } = require("cypress");

module.exports = defineConfig({
  e2e: {
    setupNodeEvents(on, config) {
      // implement node event listeners here
    },
      specPattern: "cypress/e2e/**/*.js"
  },
});

```
11- Delete all sub folders of e2e

12- Create a js file for start testing

13- write below lines in to your file:

```js

/// <reference types="Cypress" />

describe("Test", () => {
    it("Test Example", () => {
    })
})    
```
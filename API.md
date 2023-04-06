## What is API

API stands for Application Programming Interface

## Why API

API's enable your products/services to communicate with other products/services.

We can use JSON to communicate with API

JSON stands for: JavaScript Object Notation

## Pre-requisite for using API:

1- Wirte below command on terminal(bash) and it will create package.json file:

npm init

Press Enter for all questions, write your name for Author

2- Install cypress by running below command and it will create node_modules folder:

npm install --save-dev cypress@12.6.0

3- Install NPX by running below command:

npm i npx

4- Open Cypress for the first time and it will add some files to your project:

npx cypress open

After opening cypress click on "Scaffold example specs"

2 folders will be added to e2e folder, delete these 2 folders

5- add below line of code in config.js file:

specPattern: "cypress/e2e/**/*.js"

6- Delete all sub-folders of e2e folder!


## Connecting JSON-SERVER

``` js
    npx json-server --watch db.json
```

## Create JSON object:

```js
    const exampleObject = { "key": "Tim", "key2": "Jones" }
```

## Extract data from JSON object:

```js

        cy.log(exampleObject["key"])
        cy.log(exampleObject["key2"])
        cy.log(exampleObject.key)
```

## Create JSON Array:

``` js
        const exampleArrayOfValue = ["Sophie", "Rose", "Howard"]
```

## Extract data from JSON array:

```js
    cy.log(examlpeArrayeOfValue[0])
    cy.log(exampleArrayOfValue[1])
```


## MIX of above examples:

We can put both simple and array data into a Constant

```js
    const users = {
        "firstName": "Joe",
        "lastName": "Blogs",
        "Age": 30,

        "Students":[
            {
                "firstName": "Jim",
                "lastName": "Blogs",
            },
            {
                "firstName": "Sarah",
                "lastName": "Parker"
            }
        ]
    }
```

You can extract data from above object with below codes:

```js
        cy.log(users.lastName)
        cy.log(users.Students[1].firstName)
```

## Create and extract data of Array of Objects

1- Create:

```js
    const exampleArrayOfObjects = [{"key":"Luke"} , {"key2":"skywalker"}, {"key3":"22"}]
```

2- Extract:

``` js
    cy.log(exampleArrayOfObjects[0].key)
    cy.log(exampleArrayOfObjects[0].key1)
    cy.log(exampleArrayOfObjects[0].key2)
```


## Postman:
When you wanna send a request via Postman make sure that you choose "raw" and "JSON"

## Get:

To get data from your code and put it in postman!

You have to use your Localhost Link to do that!

## Post:

To add something in your code!

## Put

To Update and Edit your code!

## Delete

To Delete part of our code!

## Running Cypress From API:

npx cypress open

## Run Json Server:

npm run start

## Sending Get request and validate data from api

``` js
    it("Validate /posts api contains the correct keys and values", () => {
        cy.request({
            method: "GET",
            url: "http://localhost:3000/posts",
            headers: {
                accept: "application/json"
            }.then(response => {
            let body = JSON.parse(JSON.stringify(response.body))
            cy.log(body)

            expect(body[0]).has.property("title", "Example Json Server")
            expect(body[1]).has.property("author", "Pouria")

            body.forEach(function (item) {
                expect(item).to.have.all.keys("id", "title", "author")
                cy.log("Author:" + item["author"] + " & Tilte:" + item["title"])

            });
```

## Sending Post request

```js
describe("Post Request", () => {
    it("Creat a new post request via /posts api", () => {
        cy.request({
            method: "POST",
            url: "http://localhost:3000/posts",
            body: {
                title: "Want to learn automation testing",
                author: "Saeideh Shirmast"
            }

        }).then(response => {
            expect(response.status).to.equal(201)
        })

    })

})
```

## How to validate latest post:

we have to add below test after our post request:

``` js
    it("Validate title of latest post", () => {
        cy.request({
            method: "GET",
            url: "http://localhost:3000/posts",
            headers: {
                accept: "application/json"
            }
        }).then(response => {
            let body = JSON.parse(JSON.stringify(response.body))
            body.forEach(function (item) {
                titleOfPosts.push(item["title"])
            })
        }).then(() => {
            var latestPost = titleOfPosts[titleOfPosts.length - 1]
            expect(latestPost).to.eq("Want to learn automation testing")
        })

    })
```

## Update/Put

```js
describe("Update Request", () => {

    it("Update an existing post via /posts api", () => {
        cy.request({
            method: "PUT",
            url: "http://localhost:3000/posts/2",
            body: {
                title: "Where can I buy apples?",
                author: "Mohsen Shirmast"
            }

        }).then(response => {
            expect(response.status).to.equal(200)
        })

    })
})  
```

## Delete

```js
/// <reference types="cypress" />



describe("Delete Request", () => {

    it("Delete a post via /posts api", () => {
        cy.request({
            method: "DELETE",
            url: "http://localhost:3000/posts/8",


        }).then(response => {
            expect(response.status).to.equal(200)
        })
    })
})  
```

## XHR

XHR stands for XML Http Request

XHR is an API in the form of an object

It is used for transfer data between a web browser and a web server

## cy.intercept

It is used for tracking or listening to a request and is used to control the behavior of HTTP requests:

.as is used to save the result of "it" in a alias so we can call it later to check its value

```js
describe("Network request", () => {
    beforeEach(() => {
        cy.visit("https://example.cypress.io/commands/network-requests")
    })

    it("Get Request", () => {
        cy.intercept({
            method: "GET",
            url: " **/comments/*",

        }).as("getComment")

        cy.get(".network-btn").click()
        cy.wait("@getComment").its("response.statusCode").should("eq", 200)
    })
})

```
We can use cy.intercept method in another way:

We can get information from "response" and "request" part of our request and test them to see if it passes or not:

``` js
    it("Post Request", () => {
        cy.intercept("POST", "/comments").as("postComment")

        cy.get(".network-post").click()
        cy.wait("@postComment").should(({ request, response }) => {
            console.log(request)
            expect(request.body).to.include("email")

            console.log(response)
            expect(response.body).to.have.property("name", "Using POST in cy.intercept()")

            expect(request.headers).to.have.property("content-type")

            expect(request.headers).to.have.property("origin", "https://example.cypress.io")
        })
    })
```


## How to extract TOKEN from API

```js
    describe("API test", () => {
        const userCredential = {
            "email": email,
            "password": password
        }
        it("Login via Token (Non UI)", () => {


            cy.request("POST", "http://localhost:3000/rest/user/login", userCredential)
                .its('body').then(body => {
                    const token = body.authentication.token
                    cy.wrap(token).as("userToken")
                    cy.log("@userToken")
                })
        })
    })
```

## Question 01     
    
 What is =>

 What is fnText

        `cy.contains('#ContactUsFrm', 'Contact Us Form'). then (text => {
            const firstNameText = text.find('#field_11').text ()
            expect (firstNameText).to.contain('First name')
            })

            //Embedded commands (Closure)
            cy.get('#field_11').then(fnText => {
                cy.log(fnText.text())
                cy.log(fnText)
            })
            

        })` 


## Question 02

What is $

## Question 03

Ranorex Selocity's syntax!! How can I learn them?

## Question 04

```js 
describe ("Iterate over elements", () => {
    it ("Log information of all hair care products", () => {
    cy.visit("https://automationteststore.com/");
    cy.get ("a[href*='product/category&path=']").contains("Hair Care").click();
    cy.get (".fixed _wrapper prdocutname").each( ($el, index, $list)  => {
    cy.log ("Index: " + index + " : " + $el.text ())
});
};


```


## Question 05

What are 'attr' and 'include' (az koja avord???)`
``` js
    it.only("Validate a specific hair care product", () => {
        cy.visit("https://automationteststore.com/")
        cy.get(".thumbnail").as("productThumbnail")
        cy.get("@productThumbnail").should("have.length", 16)
        cy.get("@productThumbnail").find(".productcart").invoke('attr', 'title').should('include', 'Add to Cart')
    })
```


## Question Jadid 06

Video 97: 2:25 min: what is $LinkText and how it works and what does it do
``` js
cy.get('.thumbnail').find(".oneprice').invoke('text').as('itemPrice')
cy.get('@itemPrice').then(SlinkText =› {
var itemPrice = $linkText.split('k');
var i;
for(i = 0; i ‹ itemPrice.length; i++) {
cy.log(itemPrice[il)
})

```

Video 116: 7:49 min: Same question about $

``` js

describe ("Handling IFrame & Modals", () => {
    it ("Handle webdriveruni iframe and modal", () => {
        cy.visit("http://www.webdriveruniversity.com")
        cy.get ('#iframe").invoke('removeAttr', 'target').click({force:true})
        cy.get ('#frame').then($iframe => {
            const body = $iframe. contents ().find('body')
        })
    })
})
```

## Question Jadid 07

What Stub is?

Video 115

## Question Jadid 08

Video 117: 2:54

Why he used this part of code for clicking on a button (Did not do the same Like previous examples(Alert.js))!!!

## Ranorex Sample

Video 123: 2:45 min & 6:00 min
Video 130: 1:50 min
Video 158: 4 min
Video 164: 2:20 min  

## Question Jadid 09

``` js
describe("Verify Autocomplete dropdown list via Webdriveruni", () => {
    it("Select specific product via autocomplete list", () => {
        cy.visit("http://www.webdriveruniversity.com")
        cy.get('#autocomplete-textfield').invoke('removeAttr', 'target').click({ force: true })

        cy.get('#myInput').type('A')

        // Az inja be bad ro moshkel daram
        cy.get('#myInputautocomplete-list > *').each(($el, index, $list) => {
            const prod = $el.text()
            const productToSelect = 'Avacado'

            if (prod === productToSelect) {
                $el.click()

                cy.get('#submit-button').click()
                cy.url().should('include', productToSelect)
            }
        })

    })
```

## Question Jadid 10

    
``` js
    it.only("I should be able hold down the left mouse click button on a given element", () => {
        cy.visit("http://www.webdriveruniversity.com")
        cy.get('#actions').scrollIntoView().invoke('removeAttr', 'target').click({ force: true })

// az koja miyare inaro?
        cy.get('#click-box').trigger('mousedown', { which: 1 }).then(($element) => {
            expect($element).to.have.css('background-color', 'rgb(0, 255, 0)')
        })
    })
```

## Question Jadid 11:

``` js
        var date = new Date()
        date.setDate(date.getDate() + 1)

        var futureYear = date.getFullYear()
        var futureMonth = date.toLocaleDateString("default", { month: "long" }) //injash chi shod?
        var futureDay = date.getDate()

        cy.log("Future Year to Select:" + futureYear)
        cy.log("Future Month to select:" + futureMonth)
        cy.log("Future Day to Select:" + futureDay)
```


## Question Jadid 12:

What are request and response and how they work?

cy.wait("@newUser").then(({ request, response }) => ...

```js
    it("Test Valid Signup", () => {

        cy.intercept("POST", "**/*.realworld.io/api/users").as("newUser")

        cy.visit("http://localhost:4200")
        cy.get(".nav-link").contains("Sign up").click()
        cy.get("[placeholder='Username']").type(userName)
        cy.get("[placeholder='Email']").type("Auto_email" + randomString + "@email.com")
        cy.get("[placeholder='Password']").type("Password1")
        cy.get("button").contains("Sign up").click()

        cy.wait("@newUser").then(({ request, response }) => {
            cy.log("Request: " + JSON.stringify(request))
            cy.log("Response: " + JSON.stringify(response))

            expect(response.statusCode).to.eq(200)
            expect(request.body.user.username).to.eq(userName)
        })
```


## Question Jadid: Fixture

Video 302: 5 min

I don't know what fixture is, why it is used in below code:

```js
   it("Test Valid Login", () => {
        cy.intercept("GET", "**/tags", { fixture: 'popularTags.json' })
        cy.visit("http://localhost:4200")
        cy.get(".nav-link").contains("Sign in").click()
        cy.get("[placeholder = 'Email']").type(email)
        cy.get("[placeholder = 'Password']").type(password)
        cy.get("[type = 'submit']").click()
    })
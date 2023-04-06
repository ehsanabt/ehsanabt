## Visit

It is used to open a website:

`$ cy.visit(url)`

`$ cy.visit(url,options)`

`$ cy.visit(options)`

## Get

It is used for choosing one or more DOM element by selector

`$ cy.get("Select Element")`

** We can use cypress to choose element and then cypress will give us DOM element selection code.

## Click

It is used for clicking on chosen element.

`$ cy.get("Select Element").click()`

## Type


It is used for typing in an element

cy.get('[name="first_name"]').type('Ehsan')


## Describe

Describe is a Cypress method for grouping one or more related tests.

``` js 
describe("Inspect Automation Test Store items using chain of commands", () => {
    it("Click on the first item using item header", () => {
        cy.visit("https://www.automationteststore.com/");
        cy.get('#block_frame_featured_1769 > .thumbnails > :nth-child(1) > .fixed_wrapper > .fixed > .prdocutname').click();
    });
    it("Click on the first item using item text", () => {
        cy.visit("https://www.automationteststore.com/");
        cy.get('.prdocutname').contains('Skinsheen Bronzer Stick').click()
    });
    it("Click on the first item using index", () => {
        cy.visit("https://www.automationteststore.com/");
        cy.get('.fixed_wrapper').find('.prdocutname').eq(0).click()
    });
})

```

## Then

Then is used for doing something after for example clicking on a link:


`cy.get ("a[href$='contact']").click().then(function(linkText) {
cy.log("Clicked on link using text: " + linkText. text ())`


## Contains

When we are looking for something inside something else for example:

`cy.contains("#ContactUsForm" , 'Special text')`

## find

When we want to find something inside a selected peace of code:

`cy.contains ('#ContactUsFrm', 'Contact Us Form').find('#field_11').should('contain', 'First name')`

## Wrap

It is used to change a passed object to cypress object so we can do cypress action on it.

``` js
cy.get (".fixed_wrapper .prdocutname").each(($el, index, $list) => {
    if($el.text().includes('Curls to straight Shampoo')) {
        cy.wrap($el).click()
}
```

## Each

It is a function that works like a loop, you do something on all the specific items, you can interact with multiple elements, it gets 3 value (value, index, collection) 

``` js
cy.get (".fixed_wrapper .prdocutname").each(($el, index, $list) => {
    // $el is a wrapped jQuery element
    if($el.text().includes('Curls to straight Shampoo')) {
        // wrap this element so we can
        // use cypress commands on it
        cy.wrap($el).click()
}

```

## Invoke

It is used to use a property(Functuion) of an object. (JQuery function)

``` js
it ("Validate a specific hair care product", () =› {
    cy.visit("https://automationteststore.com/");
    cy.get ("a[href*='product/category&path=']").contains ("Hair Care").click();
I   cy.get (".fixed_wrapper .prdocutname").eq(0).invoke('text').as('productThumbnail')
});

```

## Alias (as)

It is used like a variable to save a peace of code to prevent typing it again, so we can call the alias again and again instead of typing whole peace of code!

``` js
cy.get(" .fixed_wrapper prdocutname").eq(0).invoke ('text').as('productThumbnail')
cy.get('@productThumbnail').its('length').should('be.gt', 5)
cy.get ('@productThumbnail').should('include', 'Seaweed Conditioner')
```



## removeAttr

Actually it is a jQuery function for removing an attribute from our code:

for example in the bellow contact-us id has an attribute in the code to open the following page in a new browser page. but we want to open that page inside th previous page, so we remove the target command by using removeAttr:

``` js

cy.visit("http://www.webdriveruniversity.com")
cy.get ('#contact-us').invoke('removeAttr', 'target').click()

```

## Children

``` js
  it("children() to get the children of DOM elements", () => {
    cy.get('.traversal-breadcrumb').children('.active').should('contain', 'Contact Us')
  });
```

## closest

``` js
  it("closest() to validate the closest ancestor DOM element", () => {
    cy.get('.traversal-badge').closest('ul').should('have.class', 'list-group')
  });
```

## eq

``` js

  it("eq() to retrieve a specific element based on index", () => {
    cy.get('.traversal-drinks-list > *').eq(2).should('contain', 'Milk')
  });
```

## filter

 ``` js
  it("filter() to retrieve DOM elements that match a specific selector", () => {

    cy.get('.btn-group-toggle > *').filter('.active').should('contain', 'Button-1')

  });
``` 

## find

``` js
  it("find() to retrieve DOM elements of a given selector", () => {
    cy.get('.traversal-pagination').find('li').find('a').should('have.length', 7)

  });
```

## first

``` js
  it("first() to retrieve the first DOM element within elements ", () => {

    cy.get('.traversal-table > tbody > tr > td').first().should('contain', 'Andy')
  });

```

## last

``` js
  it("last() to retrieve the last DOM element within elements", () => {

    cy.get('.traversal-table > tbody > tr > td').last().should('contain', 'Scott')
  });

```

## nextAll

``` js
  it("nextAll() to get all of the next sibling DOM elements within elements", () => {

    cy.get('.traversal-drinks-list').contains('Tea').nextAll().should('have.length', '3')
  });

```

## nextUntil

``` js
  it("nextUntil() to get all of the next sibling DOM elements within elements until another element", () => {

    cy.get('#coffee').nextUntil('#milk')
  });

```

## not

``` js

  it("not() to remove DOM element(s) from the set of elements", () => {

    cy.get('.traversal-button-states > button').not('.disabled').should('not.have.class', 'disabled')
  });
```

## parent

``` js

  it("parent() To get parent DOM element of elements", () => {

    cy.get('.traversal-mark').parent().should('contain', 'Lorem ipsum dolor sit amet')
  });
```

## parents

``` js

  it("parents() to get parents DOM element of elements", () => {

    cy.get('.traversal-cite').parents().should('match', 'blockquote')
  });
```

## prev

``` js

  it("prev() to get the previous sibling DOM element within elements", () => {

    cy.get('#sugar').prev().prev().contains('Milk')
  });
```

## prevAll

``` js

  it("prevAll() to get all previous sibling DOM elements within elements", () => {

    cy.get('.sales').prevAll().should('have.length', '2')
  });
```

## prevUntil

``` js

  it("prevUntil() to get all previous sibling DOM elements within elements until other element", () => {

    cy.get('#veggie').prevUntil('#fruits').should('have.length', 5)
  });
```

## siblings

``` js
  it("siblings() To get all sibling DOM elements of elements", () => {

    cy.get('.traversal-button-other-states .active').siblings().should('have.length', 3)
  });
```

## How to work with tables:

in this example we want to read all the table contents then find digits and sum them

``` js
it('Calculate and assert the total age of users', () => {
        var userDetails = [];
        let num = 0;
        cy.get('#thumbnail-1 td').each(($el, index, $list) => {
            userDetails[index] = $el.text();

        }).then(() => {
            var i;
            for (i = 0; i < userDetails.length; i++) {
                if (Number(userDetails[i])) {
                    num += Number(userDetails[i])
                }

                //cy.log(userDetails[i])
            }
            cy.log('Found total age:' + num)
            expect(num).to.eq(322)
        })
```


## Date

``` js
    it("Select date from datepicker", () => {
        cy.visit("http://www.webdriveruniversity.com")
        cy.get('#datepicker').invoke('removeAttr', 'target').click({ force: true })

        let date = new Date();
        date.setDate(date.getDate()) //Get current day
        cy.log(date.getDate())

        let date2 = new Date()
        date2.setDate(date.getDate() + 5)
        cy.log(date2.getDate())
    })

```


## Select File

``` js

    it("Upload file ......", () => {
        cy.visit("http://www.webdriveruniversity.com")
        cy.get('#file-upload').invoke('removeAttr', 'target').click({ force: true })

        cy.get('#myFile').selectFile('cypress/fixtures/Benz.webp')
        cy.get('#submit-button').click()
    })
```

## Before After ...

``` js 
describe('hooks', function () {
  before(function () {
    // runs once before the first test in this block
  });

  after(function () {
    // runs once after the last test in this block
  });

  beforeEach(function () {
    // runs before each test in this block
  });

  afterEach(function () {
    // runs after each test in this block
  });

  // test cases
});

// Ghabl az Test ha website morede nazar ra baz mikonad

describe("Verify checkboxes via Webdriver", () => {
before(function () {

    cy.visit("http://www.webdriveruniversity.com")
    cy.get ('#dropdown-checkboxes-radiobuttons').invoke('removeAttr', 'target').click({force:true})
    })
}
// It opens the website before each test below it!

describe("Verify checkboxes via Webdriver", () => {
beforeEach(function(){
        cy.visit("http://www.webdriveruniversity.com")
        cy.get('#dropdown-checkboxes-radiobuttons').invoke('removeAttr', 'target').click({ force: true })
    })
}
```

## Fixture

It is used for extracting data from a file:

``` js

describe("Test Contact Us form via WebdriverUni", () => {
    before(function () {
        //We created "example.json" file in "Fixture" folder
        cy.fixture('example').then(function (data) {
            //this.data = data
            globalThis.data = data;
        })
    })
    it.only("Should be able to submit a successful submission via contact us form", () => {
        //cy.visit("http://webdriveruniversity.com")
        //cy.get('#contact-us > .thumbnail').click()
        cy.visit("http://webdriveruniversity.com/Contact-Us/contactus.html")
        cy.document().should('have.property', 'charset').and('eq', 'UTF-8')
        cy.title().should('include', 'WebDriver | Contact Us')
        cy.get('[name="first_name"]').type(data.first_name)
        cy.get('[name="last_name"]').type(data.last_name)
        cy.get('[name="email"]').type(data.email)
        cy.get('textarea.feedback-input').type('Hello this is a test')
        cy.get('[type="submit"]').click()
        cy.get('h1').should('have.text', 'Thank You for your Message!')
    })
}   


//We Can Use Alias:

describe("Test Contact Us form via Automation Test Store", () => {
    before(function () {
        cy.fixture('user-details').as('user')
    })


    it("Should be able to submit a successful submission via contact us form", () => {
        cy.visit('https://automationteststore.com')
        // cy.get('.info_links_footer > :nth-child(5) > a').click()
        cy.xpath('//a[contains(@href, "contact")]').click()

        cy.get('@user').then((user) => {


            cy.get('#ContactUsFrm_first_name').type(user.first_name)
            cy.get('#ContactUsFrm_email').type(user.email)
        })
        cy.get('#ContactUsFrm_enquiry').type('This is a test!!')
        cy.get('.col-md-6 > .btn').click()

    })
})
```

## Custom Command:

Its usage is like a function!

You have to change "commands.js" file in "support" folder.

We want to create a command for below code:

``` js

    cy.get(".fixed_wrapper .prdocutname").each(($el, index, $list) => {
        if ($el.text().includes(productName)) {
            cy.wrap($el).click()
        }
    })
})

```

So add below code to "command.js"

```js
Cypress.Commands.add("selectProduct", productName => {

    cy.get(".fixed_wrapper .prdocutname").each(($el, index, $list) => {
        if ($el.text().includes(productName)) {
            cy.wrap($el).click()
        }
    })
})
```

## Environment variables

We can define a variable in cypress.config.js file by adding below code in the file:

``` js

    env: {
      first_name: 'Sarah'
    }
```

Then we can call it everywhere:

``` js

    cypress.env('variable name')
```

We can overwrite the value of Environment variable when we are running cypress in terminal:

``` js
    /node_modules/.bin/cypress run --browser chrome --headed --spec cypress cypress/e2e/webdriver-uni/contact-us.js --env first_name=Tim
```

## BaseUrl
Again we can define a URL in cypress.config.js file by adding below code:

``` js

    baseUrl: 'http://www.ijshdkjn.com'

```

Then we can call it everywhere by using below code:

``` js

    cy.visit('/')
```

So we can use "cy.visit('/')" every where instead of typing full address many times and if the URL changes we don't need to change it everywhere, just changing the URL in cypress.config.js file!

## Dynamic URL

We can define a website address as a environment variable, then use it in the code, so we have to add this line of code in cypress.config.js:

``` js

    env: {
      first_name: 'Sarah'
      webdriveruni_homepage: "http://www.webdriveruniversity.com"
    }
```

so we can add it like below in our code:

``` js

beforeEach(() => {

    cy.visit(Cypress.env("webdriveruni_homepage") + "/Contact-Us/contactus.html")
})
```

We can also add a command to open a website, so we have to add below line of code to commands.js file

``` js

    cypress.commands.add ("navigateTo_Webdriveruni_Homepage", () => {

        cy.visit(/);
    })
```

So we can call this new command everywhere:

``` js

    cy.navigateTo_Webdriveruni_Homepage()
```

We can also add a peace of URL to baseUrl like below and call the command whereever we want:

``` js

    cypress.commands.add ("navigateTo_Webdriveruni_CheckBox_Page", () => {

        cy.visit("/" + "/Dropdown-Checkboxes-RadioButtons/index.html");
    })
```



## Page Object Model

It is used to create some classes and function to call them in our code to prevent typing some extra repeating code!

After creating the "HomePage-PO.js" file we have to add below line of code in the top of the file that we want to use this file in:

``` js

import Homepage_PO from "../../../support/pageObject/webDriver-uni/Homepage-PO";
```

We create a folder under Support folder then we created a .js file an write below codes in that file:

``` js

class Homepage_PO {
    visitHomepage() {
        cy.visit(Cypress.env('webdriveruni_homepage'))
    }

    clickOn_ContactUs_Button() {
        cy.get('#contact-us').invoke('removeAttr', 'target').click({ force: 1 })
    }

}

export default Homepage_PO
```

Now we can use "visitHomepage" and "clickOn_ContactUs_Button" functions in our code:

``` js

        beforeEach(function () {
        const homepage_PO = new Homepage_PO()
        homepage_PO.visitHomepage()
        homepage_PO.clickOn_ContactUs_Button()
    })
```

## URL Timeout

It is used for checking if the website works or not, in the below code if website doesn't respond in 60 second our test will fail

Cypress has a default timeout and with below code we will over write the default timeout

``` js
    cy.get(Cypress.env("webdriveruni_homepage") , {timeout: 60000})
```


We can already add below line of code in the beginning of a block of code to change that block's timeout!

``` js

    Cypress.config('defaultCommandTimeout' , 20000)
```

Sometime we need to test a text on the screen and this text appears late so we have to give it more time to appear!

``` js
    cy.get($selector).contains(textToLocarte, {timeOut: 60000})
```


## Pause

It is used to pause executing the code to check or do manual testing or continue step by step!

We can use pause() as a new line of code, or we can use it as a chain command.

```js 
cy.pause()

    cy.get($selector).pause().contains(textToLocarte, {timeOut: 60000})
```

## Wait

``` js
cy.wait(3000)
```


## Debugger

``` js
        globalThis.data.productName.forEach(function (element) {
            cy.addProductToBasket(element).then(() => {

              debugger
            })
        })
```

``` js
    cy.get('.dropdown-toggle > .fa').click().debug()
```

## Screenshot

We can take a screenshot after a failure and when ever one of our tests fails.


We have to add below line of code to cypree.config.js file

So it will take a screenshot at failure and store it in "screenshots" foldeer

** We have to use "RUN" command on Terminal to run the test to have screenshots of failures.

Terminal has to be in "bash" mode

"./node_modules/.bin/cypress run --spec cypress/integration/examples/Webdriver-uni/Contact-us.js"

``` js
screenshotOnRunFailure: true
trashAssetBeforeRuns: true
```

We can also take a screenshot any time regardless of test fails or pass with below line of code:

``` js
    cy.screenshot()
```

We can also choose a name for screenshot file:

``` js
    cy.screenshot("Contact us test screen shot")

```

## Video

We can take a video of our test same as screenshot above

We can also change the quality of video and etc.

``` js
    
    /// worst quality

    VideoCompression: 51

    /// best quality:

    VideoCompression: 0 
```

## Screen Sizes:

We can change the screen size with below code on cypress.config.js

``` js
    viewportHeight: 1080
    viewportwidth: 1920
```

We can also change the scree size inside our test file and it will overwrite the screen size of cypress.config.js file:

``` js
    cy.viewport(width,height)
    cy.viewport('iphone-6')
```

## Clear coockie and storage

```js

    cy.clearLocalStorage()
    cy.clearCookies()
```

## Cypress Dashboard

It will store full history of test results with Videoclips, Screenshots

It will help you to share results of your test with other members of the team.

dashboard.cypress.io/login


## NPM Scripts:

We can add some scripts in package.json file to make running test and writing commands in terminal easier:


``` js
    "triggerAllTests-headless": "npx cypress run",
    "triggerAllTests-headed": "npx cypress run --headed",
    "triggerAllTests-chrome": "npx cypress run --browser chrome",
    "triggerAllTests-dashboard": "npx cypress run --record --key ed737d00-8b43-4770-bb91-de28a4b198b5",
    "triggerAllTests-webdriveruni": "npx cypress run --spec cypress cypress/integration/examples/Webdriver-uni/*"
```

Then we can use them in terminal by calling them: 

npm run triggerAllTests-webdriveruni

We can also go to package.json file and click on a script to run it.

## Retry test

We can add numbers of attempt to our test by adding below lines of code to cypress.config.js file:

``` js
  retries:{
    runMode: 0
    openMode: 1 //2 attempts
  }
```

We can also add below lines of code directly inside our test to add multiple attempts:

``` js
    it("Should be able to submit a successful submission via contact us form", {
        retries: {
            runMode: 2,
            openMode: 2
        }
    }, () => {
```

## Running a test only in a specific browser

```js
if (Cypress.isBrowser("firefox")) { ///Do it }
        else {
            const contactUs_PO = new Contact_Us_PO()
            contactUs_PO.contactForm_Submission(data.first_name, data.last_name, " ", "How can I learn Cypress?", "body", "Error: Invalid email address")
        }
```


## Alerts

We need to check alerts to see if they are like what we expect or not

** Cypress clicks on Confirm/OK button of alerts automatically. 

``` js
cy.on('window:alert', (str)=> {
  expect(str).to.equal('Hello, share this practice page and share your knowledge')
})

```

## Checkboxes

We need to test checkboxes to see if they are checked or not:

```js
 cy.get('#checkBoxOption1').check().should("be.checked").and("have.value", "option1")

```

## Choosing all items with the same attribute:

using below formula:

tagname[attribute=value]

```js
cy.get('input[type="checkbox"]').check(["option2", "option3"])

```
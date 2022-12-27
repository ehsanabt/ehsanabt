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

`describe("Inspect Automation Test Store items using chain of commands", () => {
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
})`

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


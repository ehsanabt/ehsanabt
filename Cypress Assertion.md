## Assertion

Assertions are the validation steps that determine whether the specified step of the automated test case succeeded or not. In actual, Assertions validates the desired state of your elements, objects, or application under test.

[https://docs.cypress.io/guides/references/assertions](https://docs.cypress.io/guides/references/assertions)

For example we can check if a message that is shown on the screen is the same as we expected or not!

`cy.get('Css selector').should(have.text,'Expected message')`

#### Searching something in a page:

`cy.document().should('have.property','property name').and('eq','UTF-8')`

#### Searching on page title:

`cy.title().should('include','Our text')`

#### Check if page's URL is correct:

`cy.url().should('include','URL')`
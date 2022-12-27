
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



Go to video 210 and 211


## Terminal Command for connecting all of our projects ro our Dashboard:

./node_modules/.bin/cypress run --record --key ed737d00-8b43-4770-bb91-de28a4b198b5(Record key from Dashboard Project Settings)

## Multi reports (junit reporter) Video 216 - 218

First of all we have to install junit, then run our test, then we will have some xml files, with below line of command we can merge all these xml files and result.xml will be generated.

npx junit-merge -d cypress/results/junit -o cypress/results/junit/results.xml

## mochawesome report: Video 219 - 220

First of all we have to install mochawesome then we can run all of our test and we will have some json files about our tests.

Then we can add all json files in one file:

npx mochawesome-merge cypress/results/mochawesome/*.json > mochawesome.json && npx marge mochawesome.json

We will have a HTML file too with all information about our tests.

## Make scripts in package.json file

we can make some scripts in package.json file to make working with terminal easier and we don't need to write script again:
```js
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "triggerAllTests-headless": "npx cypress run",
    "triggerAllTests-headed": "npx cypress run --headed",
    "triggerAllTests-chrome": "npx cypress run --browser chrome",
    "triggerAllTests-dashboard": "npx cypress run --record --key ed737d00-8b43-4770-bb91-de28a4b198b5",
    "triggerAllTests-webdriveruni": "npx cypress run --spec cypress cypress/integration/examples/Webdriver-uni/*",
    "junit-merge": "npx junit-merge -d cypress/results/junit -o cypress/results/junit/results.xml",
    "delete-junit-report": "rm -rf cypress/results/junit/results.xml",
    "delete-results": "rm -rf cypress/results/* || true",
    "mochawesome-merge": "npx mochawesome-merge cypress/results/mochawesome/*.json > mochawesome.json && npx marge mochawesome.json",
    "delete-mochawesome-report": "rm -rf mochawesome-report/* || true"

 ```

 We can also use other script in a new script:

 ```js
    "cypress-regression-pack": "npm run delete-results && npm run delete-mochawesome-report && npm run triggerAllTests-headless && npm run mochawesome-merge"
 ```


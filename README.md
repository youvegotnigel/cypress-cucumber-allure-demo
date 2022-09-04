# cypress-cucumber-allure-demo
This project is created to show how we can leverage Cucumber BDD framework in Cypress. Steps involved in configuring your project are following:

## Pre-Requisites
* Node JS and NPM - [Node](https://nodejs.org/en/download/) 
* IDE - [VS Code](https://code.visualstudio.com/download) 

## Set Up
* Clone the project and run ```npm init i``` to  install all dependencies.  

## Cypress Help
```
npx cypress run --help
```  

## Dependencies
* cypress - v10.7
* multiple-cucumber-html-reporter - v1.21.4
* cucumber-json-report-formatter - v0.0.9
* cypress-xpath - v2.0.1
* moment - v2.29.4
* moment-timezone - v0.5.37
* @badeball/cypress-cucumber-preprocessor - v12.1.0
* @bahmutov/cypress-esbuild-preprocessor -  v2.1.3
* @shelex/cypress-allure-plugin - v2.29.0

## Configure VS Code

### Use `ctrl + shift + p` and search for  `Preferences: Open Settings (JSON)` and open VS Codes settings. Add the following in `settings.json`

```
 "[feature]":{
        "editor.formatOnSave": true,
    },
    "cucumberautocomplete.strictGherkinCompletion": true,
    "cucumberautocomplete.steps": [
        "cypress/integration/**/*.js",
        "cypress/e2e/**/*.js",
    ]
```

## Features
- BDD Framework
- Page Object Model
- Cucumber HTML Report
- Allure Report

## Documentation
- https://www.youtube.com/watch?v=FlQ9Carxeds
- https://testersdock.com/cypress-cucumber-bdd/
- https://github.com/badeball/cypress-cucumber-preprocessor/blob/master/docs/readme.md
- https://www.npmjs.com/package/@badeball/cypress-cucumber-preprocessor
- https://github.com/Shelex/cypress-allure-plugin
- https://www.npmjs.com/package/cypress-xpath

## Github Issues
- https://github.com/cucumber/json-formatter/issues/13


## How to Run and Generate Report

### GUI Mode
```
npx cypress open
```  

### CLI Mode

#### Run All Features and Generate Allure Report
```
npm run allure:clear
npm run cy:run
npm run allure:report
```

#### Run Specific Feature
```
npx cypress run --browser "chrome" --spec "cypress/integration/LoginTest/Login.feature"
or
npx cypress-tags run -g 'cypress/integration/LoginTest/Login.feature' --browser "chrome"
or
npx cypress-tags run --browser "chrome" -e tags=@stage --spec "cypress/integration/LoginTest/Login.feature" --env configFile=qa
npm run allure:report
```  

#### Run Specific Feature with Percy Visual Testing
```
npm run allure:clear
$env:PERCY_TOKEN = "<token>"
npx cypress-tags run --browser "chrome" -e tags=@stage --spec "cypress/integration/LoginTest/Login.feature" --env configFile=qa
npm run cy:report
npm run allure:report
``` 

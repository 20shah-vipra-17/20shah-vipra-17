
# Start Automation with Kathalon

## Feature and benefits of Kathalon
    1. Cypress is a next generation front end testing tool built for the modern web.
    2. It is fast, easy and reliable testing for anything that runs in a browser.
    3. It is a free and open source tool.
    4. It is a complete end-to-end testing experience.
    5. It is a fast and reliable testing for anything that runs in a browser.
    6. It is a fast and easy to set up.
    7. It is a fast and easy to write tests.
    8. It is a fast and easy to debug.
    9. It is a fast and easy to run tests.
    10. It is a fast and easy to record tests.  
    11. It is a fast and easy to run tests in CI.
    12. It is a fast and easy to run tests in parallel.
    13. It is a fast and easy to run tests in Docker.
    14. It is a fast and easy to run tests in the cloud.


## General Project Structure
    1. cypress/fixtures/helper: This folder contains all the page class files.
    2. cypress/envconfig: This folder contains all the test data related files, this can be used to run the test cases in multiple environment.
    3. cypress/e2e: This folder contains all the test cases related files.
    4. cypress/reports: This folder contains test case report which will be generated after the execution.
    5. cypress/support: This folder contains all the support related files.
    6. cypress/downloads: This folder contains all downloaded files and will be used while verifying the downloaded items.
    7. cypress/screenshots: This folder contains all the screenshots related files.
    10. cypress/reports: This folder contains all the reports related files.
    11. cypress.config.js will be used to configure the cypress related configurations.
    12. package.json will be used to configure the cypress related dependencies.

 
General Project Structure using diagram:
---------------------------------
    .
    ├── cypress                        # Main automation module folder created by default by Cypress
    │  ├── downloads --------------- folder to keep all the downloaded files at run time       
    │  ├── e2e  
    │  │   └── sub-folder ---------- Keep test automated test cases here and you can create multiple sub-folder as per the actual automation need
    │  └── envconfig --------------- keep your dynamic test data here, these files can be used at run time to execute the same test cases on multiple environments.
    |  └── fixtures ---------------- keep all the helper files here, you can design the automation using page object model by creating individual folder/page class files
    |   └── reports ---------------- execution reports will be available in this folder 
    │    
    └── README.md

# Initial setup to start with Cypress:
    1. Install node 12 or 14 or above version 
    2. Open Visual studio
    3. Import the project or click on the open folder and just open the project.
    4. Open the Terminal in the visual studio code
    5. Run the command: npm init if you are doing it from scratch
    6. Run the command: npm install cypress --save-dev
    7. Verify that node_modules folder has been created

    8. Run the command: npx cypress open or npm cypress open 
    9. Execute your test cases one by one

    10. If you want to execute entire test cases then Run the command: npx cypress run

    11. If you want to execute entire test cases with some specific browser then use the command: npx cypress run --browser chrome

    12. To execute any particular specf files: npx cypress run --spec cypress/e2e/connectsecure/TestLoginPage.cy.js

    13. To execute particular spec files on particular browser: npx cypress run --spec cypress/e2e/connectsecure/TestLoginPage.cy.js --browser chrome

    14. To execute all spec files inside any folder : npx cypress run --spec cypress/e2e/connectsecure/*.cy.js --browser chrome

    15. To clear the cache Run the command: npm cache clear --force

    16. To execute the test case with some specific environment:
        npx cypress open --config-file cypress/envconfig/qa.config.js
        OR
        npx cypress open --config-file cypress/envconfig/prod.config.js 
        OR 
        npx cypress open --config-file cypress/envconfig/onPrem.config.js

    17. To execute entire test cases with some specific env and with specific browser:
        npx cypress run --browser chrome
        OR
        npx cypress run --config-file cypress/envconfig/qa.config.js --spec cypress/e2e/connectsecure/* --browser chrome
        OR
        npx cypress run --config-file cypress/envconfig/prod.config.js --spec cypress/e2e/connectsecure/* --browser chrome
        OR
        npx cypress run --config-file cypress/envconfig/onPrem.config.js --spec cypress/e2e/connectsecure/* --browser chrome
    
    18. To execute any particular tags, use below command:
        npx cypress run --config-file cypress/envconfig/qa.config.js --spec cypress/e2e/connectsecure/* --browser chrome --env grepTags='@sanity'
        OR
        npx cypress run --config-file cypress/envconfig/prod401.config.js --spec cypress/e2e/connectsecure/* --browser chrome --env grepTags='@sanity'
        OR
        npx cypress run --config-file cypress/envconfig/onPrem.config.js --spec cypress/e2e/connectsecure/* --browser chrome --env grepTags='@sanity'


# Important key points
    1. Default timeout period configured is 45 seconds, if required some extra timeout period then use cy.wait or declare some utility methods for the same.
    2. Do not make unneccessary changes into these files package.json, package-lock.json, cypress.config.js, e2e.js, command.js
    3. Do not push dead code or unused lines.
    4. Declare Javascript doc for each and every utility methods.
    5. Do not push changes related to baseurls - else it may cause some issue while selecting the correct environment. 

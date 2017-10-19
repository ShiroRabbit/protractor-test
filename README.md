# protractor-test
Just some startup protractor stuff

## To Begin
### These steps will get protractor and the selenium webdriver stuff set up
* $ npm install -g protractor //installs protractor globally
* $ webdriver-manager update //unpacks and updates webdriver files, defaults are chrome and firefox

### Start up webdriver
* $ webdriver-manager start //this must always be done in a separate terminal to keep the local instance running. navigate to http://localhost:4444/wd/hub; if you see a webpage with "Create Session", your webdriver is ready to go to work

### Write some tests
* Use jasmine, yo; first test will be navigating to github
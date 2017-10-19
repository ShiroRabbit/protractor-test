# protractor-test
Just some startup protractor stuff

## To Begin
### These steps will get protractor and the selenium webdriver stuff set up
* $ npm install -g protractor //installs protractor globally
* $ webdriver-manager update //unpacks and updates webdriver files, defaults are chrome and firefox

### Start up webdriver
* $ webdriver-manager start //this must always be done in a separate terminal to keep the local instance running. navigate to http://localhost:4444/wd/hub; if you see a webpage with "Create Session", your webdriver is ready to go to work

### Suggested File Structure
|-- test
    |-- unit (stick unit test crap in here if it exists)
    |-- e2e (protractor stuff)
      |-- page-objects >these are the pages that are used to setup a suite. its far better to map page objects then write a massive file of individual tests that reuse the same logic over and over. unsure if you guys have progressed this far. see http://www.protractortest.org/#/page-objects for more info
          home-page.js
          profile-page.js
          contacts-page.js
      home-spec.js // this is functionally the same as the conf.js file mentioned in the tutorial - its simply the file that you command to execute (e.g. protractor home-spec.js) it should not live in the page objects folder
      profile-spec.js
      contacts-spec.js

### Write some tests
* Use jasmine, yo; first test will be navigating to github
* Create a spec file (using the above file structure, this would live in e2e) that will navigate to github and log you in
// spec.js
describe('Protractor Demo App', function() {
  it('should have a title', function() {
    browser.get('http://juliemr.github.io/protractor-demo/');//replace me

    expect(browser.getTitle()).toEqual('Super Calculator');//replace me
  });
});
* Next, create a config file (this will live outside of e2e, where the xx-spec.js files live in the above structure)
// conf.js
exports.config = {
  framework: 'jasmine',
  seleniumAddress: 'http://localhost:4444/wd/hub',
  specs: ['spec.js']
}
* With your webdriver instance running via one terminal, create another terminal and run the test
$ protractor conf.js

### If you run into issues, google or let me know and i'll try to help puzzle it out


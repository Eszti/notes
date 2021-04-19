# Frontend Testing

- headless browser: browser without GUI, good for testing, renders like real browsers

## Cypress

- end-to-end browser testing framework
- [Puppeteer](https://github.com/puppeteer/puppeteer)
  - headless library
- follows the `conditional testing` principle `If X, then Y, else Z`
- [cypress testing library](https://testing-library.com/docs/cypress-testing-library/intro/)
  - allows dom-testing queries
  - aria-labels can be used
    - provides the user with recognisable names of the object

### Commands

```js
// Add new command
Cypress.Commands.add("clickCancel", (pattern) => {
  testCancelFlow(pattern);
});

// Call
cy.clickCancel(PAGES.OVERVIEW.title);
```

## Jest

- [jest](https://jestjs.io/)
- javascript test framework
- mostly for unit & integration
- runs a low level, plain JavaScript
- transformers
  - [esbuild-jest](https://github.com/aelbore/esbuild-jest)
    - fast
    - ts, js, tsx, jsx
- mocking
- exceptions
- snapshot tests
- setting: `jest.config.js`
- set up moduleDirectories for using relative paths
  - `moduleDirectories: ["node_modules", path.join(__dirname, "src")]`

## Cucumber

- [Cucumber](https://cucumber.io/)
- write human readable tests
- mostly for e2e
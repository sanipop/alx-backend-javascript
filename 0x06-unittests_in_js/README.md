# Unittests in JS

## Overview

This project is focused on understanding and applying unit testing in JavaScript using various tools and libraries such as Mocha, Chai, and Sinon. The primary goal is to ensure that you can write effective test suites for JavaScript applications, covering both basic and advanced testing techniques.

## Curriculum

### Short Specializations
- **Unittests in JS**
  - **Topics Covered:**
    - UnitTests
    - Back-end Development
    - JavaScript (ES6)
    - NodeJS
    - ExpressJS
    - Mocha
  
  - **Weight:** 1
  - **Project Timeline:** 
    - Start: July 24, 2024, 6:00 AM
    - End: July 26, 2024, 6:00 AM
    - Checker Release: July 24, 2024, 6:00 PM
    - Auto Review: At the deadline

## Resources

### Read or Watch:
- [Mocha documentation](https://mochajs.org/)
- [Chai](https://www.chaijs.com/)
- [Sinon](https://sinonjs.org/)
- [Express](https://expressjs.com/)
- [Request](https://github.com/request/request)
- [How to Test NodeJS Apps using Mocha, Chai and SinonJS](https://dev.to)

### Learning Objectives
By the end of this project, you should be able to:
- Use Mocha to write a test suite.
- Use different assertion libraries (Node or Chai).
- Present long test suites.
- Use spies and stubs.
- Understand hooks and their usage.
- Perform unit testing with async functions.
- Write integration tests with a small node server.

### Requirements
- **Environment:** Ubuntu 18.04 using Node 12.x.x
- **Editors:** vi, vim, emacs, Visual Studio Code
- **File Endings:** All files should end with a new line.
- **README:** A README.md file is mandatory.
- **Code Extensions:** Use the `.js` extension.
- **Testing Command:** Use `npm run test *.test.js` to run tests without errors or warnings.

## Tasks

### Task 0: Basic test with Mocha and Node assertion library
- **Install Mocha using npm.**
- **Set up scripts in `package.json` for running Mocha with `npm test`.**
- **Create `0-calcul.js`** with a function `calculateNumber(a, b)` that rounds `a` and `b` and returns their sum.
- **Create `0-calcul.test.js`** with test cases for `calculateNumber`.
- **Ensure tests pass using `npm test 0-calcul.test.js`.**

### Task 1: Combining descriptions
- **Create `1-calcul.js`** with an updated `calculateNumber(type, a, b)` function handling `SUM`, `SUBTRACT`, and `DIVIDE`.
- **Create `1-calcul.test.js`** with organized test cases using `describe`.
- **Ensure tests pass using `npm test 1-calcul.test.js`.**

### Task 2: Basic test using Chai assertion library
- **Copy `1-calcul.js` to `2-calcul_chai.js`.**
- **Copy `1-calcul.test.js` to `2-calcul_chai.test.js`.**
- **Rewrite the test suite using Chai's `expect` style.**
- **Ensure tests pass using `npm test 2-calcul_chai.test.js`.**

### Task 3: Spies
- **Install Sinon using npm.**
- **Create `utils.js` with a `Utils` module and `calculateNumber` function.**
- **Create `3-payment.js`** with `sendPaymentRequestToApi(totalAmount, totalShipping)`.
- **Create `3-payment.test.js`** with a test suite using `sinon.spy` to validate function calls.
- **Ensure tests pass using `npm test 3-payment.test.js`.**

### Task 4: Stubs
- **Create `4-payment.js`** (same as `3-payment.js`).
- **Create `4-payment.test.js`** (same as `3-payment.test.js`).
- **Use `sinon.stub` to mock `Utils.calculateNumber` and validate calls and logs.**
- **Ensure tests pass using `npm test 4-payment.test.js`.**

### Task 5: Hooks
- **Copy `4-payment.js` to `5-payment.js`.**
- **Create `5-payment.test.js`** with tests for `sendPaymentRequestToAPI` using `beforeEach` and `afterEach` hooks.
- **Ensure tests pass using `npm test 5-payment.test.js`.**

### Task 6: Async tests with done
- **Create `6-payment_token.js`** with `getPaymentTokenFromAPI(success)` returning a resolved promise.
- **Create `6-payment_token.test.js`** testing `getPaymentTokenFromAPI(true)` using the `done` callback.
- **Ensure tests pass using `npm test 6-payment_token.test.js`.**

### Task 7: Skip
- **Using `7-skip.test.js`,** make the suite pass without fixing/removing failing tests by skipping them.
- **Ensure tests pass using `npm test 7-skip.test.js`.**

### Task 8: Basic Integration testing
- **Create `8-api` folder** with `package.json` for dependencies.
- **Create `api.js`** with an Express server listening on port 7865 and a basic GET `/` route.
- **Create `api.test.js`** with integration tests for the index page.
- **Ensure tests pass using `npm test api.test.js`.**

### Task 9: Regex integration testing
- **Create `9-api` folder** (same as `8-api`).
- **Modify `api.js`** with a GET `/cart/:id` route validating `:id` as a number.
- **Modify `api.test.js`** with tests for the `/cart/:id` route.
- **Ensure tests pass using `npm test api.test.js`.**

### Task 10: Deep equality & Post integration testing
- **Create `10-api` folder** (same as `9-api`).
- **Modify `api.js`** with GET `/available_payments` and POST `/login` routes.
- **Modify `api.test.js`** with tests for the new endpoints.
- **Ensure tests pass using `npm test api.test.js`.**

## Repository Structure

```
alx-backend-javascript/
├── 0x06-unittests_in_js/
│   ├── 0-calcul.js
│   ├── 0-calcul.test.js
│   ├── 1-calcul.js
│   ├── 1-calcul.test.js
│   ├── 2-calcul_chai.js
│   ├── 2-calcul_chai.test.js
│   ├── 3-payment.js
│   ├── 3-payment.test.js
│   ├── 4-payment.js
│   ├── 4-payment.test.js
│   ├── 5-payment.js
│   ├── 5-payment.test.js
│   ├── 6-payment_token.js
│   ├── 6-payment_token.test.js
│   ├── 7-skip.test.js
│   ├── 8-api/
│   │   ├── package.json
│   │   ├── api.js
│   │   ├── api.test.js
│   ├── 9-api/
│   │   ├── package.json
│   │   ├── api.js
│   │   ├── api.test.js
│   ├── 10-api/
│   │   ├── package.json
│   │   ├── api.js
│   │   ├── api.test.js
├── README.md
```

## License

This project is licensed under the terms of the ALX license. All rights reserved.

## Authors

- [ALX](https://www.alxafrica.com/)

---

Feel free to reach out if you have any questions or need further assistance!

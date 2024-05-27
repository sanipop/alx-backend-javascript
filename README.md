# ALX Backend JavaScript - ES6 Basics

This repository contains a series of tasks to help you practice and understand ES6 features in JavaScript.

## Setup

### Install NodeJS 12.11.x

1. In your home directory, run the following commands to set up NodeJS:
    ```sh
    curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
    sudo bash nodesource_setup.sh
    sudo apt install nodejs -y
    ```

2. Verify the installation:
    ```sh
    nodejs -v
    # v12.11.1
    npm -v
    # 6.11.3
    ```

### Install Jest, Babel, and ESLint

1. In your project directory, use the supplied `package.json` to install Jest, Babel, and ESLint:
    ```sh
    npm install
    ```

## Configuration Files

Add the following files to your project directory:

### `package.json`

<details>
<summary>Click here to show/hide file contents</summary>

```json
{
  "name": "es6_basic",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "node",
    "test": "jest"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@babel/cli": "^7.14.3",
    "@babel/core": "^7.14.3",
    "@babel/preset-env": "^7.14.2",
    "babel-jest": "^26.6.3",
    "eslint": "^7.27.0",
    "jest": "^26.6.3"
  }
}
```

</details>

### `babel.config.js`

<details>
<summary>Click here to show/hide file contents</summary>

```js
module.exports = {
  presets: [
    ['@babel/preset-env', { targets: { node: 'current' } }],
  ],
};
```

</details>

### `.eslintrc.js`

<details>
<summary>Click here to show/hide file contents</summary>

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
    jest: true,
  },
  extends: [
    'eslint:recommended',
    'plugin:react/recommended',
    'airbnb',
  ],
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: 'module',
  },
  plugins: [
    'react',
  ],
  rules: {
    'react/jsx-filename-extension': [1, { extensions: ['.js', '.jsx'] }],
  },
};
```

</details>

### Final Setup

Run `npm install` from the terminal in your project folder to install all necessary project dependencies.

## Tasks

### 0. Const or let?

**File:** `0-constants.js`

Modify the following functions:
- Use `const` for `taskFirst`.
- Use `let` for `taskNext`.

```js
export function taskFirst() {
  const task = 'I prefer const when I can.';
  return task;
}

export function getLast() {
  return ' is okay';
}

export function taskNext() {
  let combination = 'But sometimes let';
  combination += getLast();
  return combination;
}
```

### 1. Block Scope

**File:** `1-block-scoped.js`

Ensure that variables inside `taskBlock` are not overwritten inside the conditional block.

```js
export default function taskBlock(trueOrFalse) {
  const task = false;
  const task2 = true;

  if (trueOrFalse) {
    const task = true;
    const task2 = false;
  }

  return [task, task2];
}
```

### 2. Arrow Functions

**File:** `2-arrow.js`

Rewrite the function to use ES6’s arrow syntax.

```js
export default function getNeighborhoodsList() {
  this.sanFranciscoNeighborhoods = ['SOMA', 'Union Square'];

  this.addNeighborhood = (newNeighborhood) => {
    this.sanFranciscoNeighborhoods.push(newNeighborhood);
    return this.sanFranciscoNeighborhoods;
  };
}
```

### 3. Parameter Defaults

**File:** `3-default-parameter.js`

Condense the function using default parameter values.

```js
export default function getSumOfHoods(initialNumber, expansion1989 = 89, expansion2019 = 19) {
  return initialNumber + expansion1989 + expansion2019;
}
```

### 4. Rest Parameter Syntax

**File:** `4-rest-parameter.js`

Return the number of arguments passed using rest parameter syntax.

```js
export default function returnHowManyArguments(...args) {
  return args.length;
}
```

### 5. Spread Syntax

**File:** `5-spread-operator.js`

Concatenate arrays and a string using spread syntax.

```js
export default function concatArrays(array1, array2, string) {
  return [...array1, ...array2, ...string];
}
```

### 6. Template Literals

**File:** `6-string-interpolation.js`

Rewrite the return statement using a template literal.

```js
export default function getSanFranciscoDescription() {
  const year = 2017;
  const budget = {
    income: '$119,868',
    gdp: '$154.2 billion',
    capita: '$178,479',
  };

  return `As of ${year}, it was the seventh-highest income county in the United States, with a per capita personal income of ${budget.income}. As of 2015, San Francisco proper had a GDP of ${budget.gdp}, and a GDP per capita of ${budget.capita}.`;
}
```

### 7. Object Property Value Shorthand

**File:** `7-getBudgetObject.js`

Use shorthand syntax for object properties.

```js
export default function getBudgetObject(income, gdp, capita) {
  return { income, gdp, capita };
}
```

### 8. Computed Property Names

**File:** `8-getBudgetCurrentYear.js`

Use computed property names in the object.

```js
function getCurrentYear() {
  const date = new Date();
  return date.getFullYear();
}

export default function getBudgetForCurrentYear(income, gdp, capita) {
  return {
    [`income-${getCurrentYear()}`]: income,
    [`gdp-${getCurrentYear()}`]: gdp,
    [`capita-${getCurrentYear()}`]: capita,
  };
}
```

### 9. ES6 Method Properties

**File:** `9-getFullBudget.js`

Use ES6 method properties in the object.

```js
import getBudgetObject from './7-getBudgetObject.js';

export default function getFullBudgetObject(income, gdp, capita) {
  const budget = getBudgetObject(income, gdp, capita);
  return {
    ...budget,
    getIncomeInDollars(income) {
      return `$${income}`;
    },
    getIncomeInEuros(income) {
      return `${income} euros`;
    },
  };
}
```

### 10. For...of Loops

**File:** `10-loops.js`

Use ES6’s `for...of` loop and let instead of var.

```js
export default function appendToEachArrayValue(array, appendString) {
  const result = [];
  for (const value of array) {
    result.push(appendString + value);
  }
  return result;
}
```

### 11. Iterator

**File:** `11-createEmployeesObject.js`

Return an object with the department name as a key and the employees as values.

```js
export default function createEmployeesObject(departmentName, employees) {
  return {
    [departmentName]: employees,
  };
}
```

### 12. Report Object

**File:** `12-createReportObject.js`

Return an object containing the key `allEmployees` and a method property `getNumberOfDepartments`.

```js
export default function createReportObject(employeesList) {
  return {
    allEmployees: { ...employeesList },
    getNumberOfDepartments(employeesList) {
      return Object.keys(employeesList).length;
    },
  };
}
```

## Execution Examples

To run the examples, use the following commands:

```sh
npm run dev 0-main.js
npm run dev 1-main.js
npm run dev 2-main.js
npm run dev 3-main.js
npm run dev 4-main.js
npm run dev 5-main.js
npm run dev 6-main.js
npm run dev 7-main.js
npm run dev 8-main.js
npm run dev 9-main.js
npm run dev 10-main.js
npm run dev 11-main.js
npm run dev 12-main.js
```

## Repository

- **GitHub Repository:** [alx-backend-javascript](https://github.com/yourusername/alx-backend-javascript)
- **Directory:** `0x00-ES6_basic`

## Author

- Your Name

Feel free to modify and enhance the tasks as needed!

# ALX Backend JavaScript - ES6 Promises

## Setup

### Prerequisites
- NodeJS 12.11.x
- npm 6.11.3

### Installing NodeJS
Run the following commands in your home directory to install NodeJS 12.11.x:

```bash
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt install nodejs -y
```

Verify the installation:

```bash
nodejs -v
# Should output: v12.11.1

npm -v
# Should output: 6.11.3
```

### Installing Jest, Babel, and ESLint

Navigate to your project directory and install Jest, Babel, and ESLint using the provided `package.json`:

```bash
npm install
```

### Configuration Files

Add the following configuration files to your project directory:

#### package.json
```json
// Click to show/hide file contents
```

#### babel.config.js
```js
// Click to show/hide file contents
```

#### utils.js
Use this file when you need `uploadPhoto` and `createUser` functions.

```js
// Click to show/hide file contents
```

#### .eslintrc.js
```js
// Click to show/hide file contents
```

After adding the files, run:

```bash
npm install
```

## Response Data Format

### uploadPhoto
Returns a response with the format:
```json
{
  "status": 200,
  "body": "photo-profile-1"
}
```

### createUser
Returns a response with the format:
```json
{
  "firstName": "Guillaume",
  "lastName": "Salva"
}
```

## Tasks

### 0. Keep every promise you make and only make promises you can keep

Create a prototype function `getResponseFromAPI()` that returns a Promise.

```js
import getResponseFromAPI from "./0-promise.js";

const response = getResponseFromAPI();
console.log(response instanceof Promise);  // true
```

### 1. Don't make a promise...if you know you can't keep it

Create a function `getFullResponseFromAPI(success)` that returns a promise.

```js
import getFullResponseFromAPI from './1-promise';

console.log(getFullResponseFromAPI(true));  // Promise { { status: 200, body: 'Success' } }
console.log(getFullResponseFromAPI(false));  // Promise { <rejected> Error: The fake API is not working currently }
```

### 2. Catch me if you can!

Create a function `handleResponseFromAPI(promise)` that appends three handlers to the function:

```js
import handleResponseFromAPI from "./2-then";

const promise = Promise.resolve();
handleResponseFromAPI(promise);  // Got a response from the API
```

### 3. Handle multiple successful promises

Create a function `handleProfileSignup()` that logs `body firstName lastName` to the console.

```js
import handleProfileSignup from "./3-all";

handleProfileSignup();  // photo-profile-1 Guillaume Salva
```

### 4. Simple promise

Create a function `signUpUser(firstName, lastName)` that returns a resolved promise with an object:

```js
import signUpUser from "./4-user-promise";

console.log(signUpUser("Bob", "Dylan"));  // Promise { { firstName: 'Bob', lastName: 'Dylan' } }
```

### 5. Reject the promises

Create a function `uploadPhoto(fileName)` that returns a promise rejecting with an error:

```js
import uploadPhoto from './5-photo-reject';

console.log(uploadPhoto('guillaume.jpg'));  // Promise { <rejected> Error: guillaume.jpg cannot be processed }
```

### 6. Handle multiple promises

Create a function `handleProfileSignup(firstName, lastName, fileName)`:

```js
import handleProfileSignup from './6-final-user';

console.log(handleProfileSignup("Bob", "Dylan", "bob_dylan.jpg"));  // Promise { <pending> }
```

### 7. Load balancer

Create a function `loadBalancer(chinaDownload, USDownload)` that returns the value of the first resolved promise:

```js
import loadBalancer from "./7-load_balancer";

const ukSuccess = 'Downloading from UK is faster';
const frSuccess = 'Downloading from FR is faster';

const promiseUK = new Promise((resolve) => setTimeout(resolve, 100, ukSuccess));
const promiseUKSlow = new Promise((resolve) => setTimeout(resolve, 400, ukSuccess));
const promiseFR = new Promise((resolve) => setTimeout(resolve, 200, frSuccess));

const test = async () => {
    console.log(await loadBalancer(promiseUK, promiseFR));  // Downloading from UK is faster
    console.log(await loadBalancer(promiseUKSlow, promiseFR));  // Downloading from FR is faster
}

test();
```

### 8. Throw error / try catch

Create a function `divideFunction(numerator, denominator)`:

```js
import divideFunction from './8-try';

console.log(divideFunction(10, 2));  // 5
console.log(divideFunction(10, 0));  // Error: cannot divide by 0
```

### 9. Throw an error

Create a function `guardrail(mathFunction)`:

```js
import guardrail from './9-try';
import divideFunction from './8-try';

console.log(guardrail(() => divideFunction(10, 2)));  // [ 5, 'Guardrail was processed' ]
console.log(guardrail(() => divideFunction(10, 0)));  // [ 'Error: cannot divide by 0', 'Guardrail was processed' ]
```

### 10. Await / Async

Create an async function `asyncUploadUser()`:

```js
import asyncUploadUser from "./100-await";

const test = async () => {
    const value = await asyncUploadUser();
    console.log(value);  // { photo: { status: 200, body: 'photo-profile-1' }, user: { firstName: 'Guillaume', lastName: 'Salva' } }
};

test();
```

## Repository

GitHub repository: `alx-backend-javascript`
Directory: `0x01-ES6_promise`

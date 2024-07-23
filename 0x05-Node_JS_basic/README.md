# NodeJS Basics

## Project Overview

This project explores the basics of Node.js and Express.js. By the end of the project, you'll be able to:

- Run JavaScript using Node.js
- Use Node.js modules and specific modules to read files
- Access command line arguments and the environment
- Create small HTTP servers using both Node.js and Express.js
- Use ES6 with Node.js through Babel-node
- Use Nodemon to speed up development

## Resources

- [Node.js Getting Started](https://nodejs.org/en/docs/guides/getting-started-guide/)
- [Process API Documentation](https://nodejs.org/api/process.html)
- [Child Process](https://nodejs.org/api/child_process.html)
- [Express Getting Started](https://expressjs.com/en/starter/installing.html)
- [Mocha Documentation](https://mochajs.org/)
- [Nodemon Documentation](https://nodemon.io/)

## Learning Objectives

- Run JavaScript using Node.js
- Use Node.js modules
- Use Node.js to read files
- Access command line arguments and the environment
- Create HTTP servers using Node.js and Express.js
- Use ES6 with Node.js and Babel-node
- Use Nodemon for faster development

## Requirements

- Editors: `vi`, `vim`, `emacs`, `Visual Studio Code`
- Files interpreted/compiled on Ubuntu 18.04 LTS using Node (version 12.x.x)
- Files should end with a new line
- A `README.md` file at the root of the project directory is mandatory
- Use `.js` extension for code files
- Tests executed using `npm run test`
- Code verified against lint using ESLint
- Code must pass all tests and lint checks (`npm run full-test`)
- Functions/classes exported using `module.exports = myFunction;`

## Provided Files

- `database.csv`: Contains student data
- `package.json`: Project dependencies
- `babel.config.js`: Babel configuration
- `.eslintrc.js`: ESLint configuration

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/alx-backend-javascript.git
   ```
2. Navigate to the project directory:
   ```sh
   cd alx-backend-javascript/0x05-Node_JS_basic
   ```
3. Install the dependencies:
   ```sh
   npm install
   ```

## Usage

### Task 0: Executing Basic JavaScript with Node.js
```sh
node 0-console.js
```

### Task 1: Using Process stdin
```sh
node 1-stdin.js
```

### Task 2: Reading a File Synchronously with Node.js
```sh
node 2-read_file.js
```

### Task 3: Reading a File Asynchronously with Node.js
```sh
node 3-read_file_async.js
```

### Task 4: Creating a Small HTTP Server using Node's HTTP Module
```sh
node 4-http.js
```

### Task 5: Creating a More Complex HTTP Server using Node's HTTP Module
```sh
node 5-http.js database.csv
```

### Task 6: Creating a Small HTTP Server using Express
```sh
node 6-http_express.js
```

### Task 7: Creating a More Complex HTTP Server using Express
```sh
node 7-http_express.js database.csv
```

### Task 8: Organizing a Complex HTTP Server using Express
```sh
npm run dev
```

## Contribution Guidelines

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Create a new Pull Request.

## License

This project is licensed under the MIT License.

---

Feel free to update this README file with any additional details specific to your project.

# TypeScript Curriculum Project

## Overview

This project aims to teach the fundamentals of TypeScript through a series of practical tasks. By the end of the project, participants will understand TypeScript's basic types, interfaces, classes, functions, and advanced topics such as generics, namespaces, and declaration merging.

## Learning Objectives

By the end of this project, you should be able to explain the following concepts without external help:
- Basic types in TypeScript
- Interfaces, Classes, and functions
- Working with the DOM in TypeScript
- Generic types
- Using namespaces
- Merging declarations
- Using ambient namespaces to import external libraries
- Basic nominal typing with TypeScript

## Requirements

- Allowed editors: vi, vim, emacs, Visual Studio Code
- All files should end with a new line
- All files will be transpiled on Ubuntu 18.04
- TypeScript scripts will be checked with Jest (version 24.9.*)
- A `README.md` file at the root of the project folder is mandatory
- Code should use the `.ts` extension when possible
- The TypeScript compiler should not show any warnings or errors when compiling your code

## Project Structure

The project is divided into several tasks, each focusing on different aspects of TypeScript. Configuration files (`package.json`, `.eslintrc.js`, `tsconfig.json`, and `webpack.config.js`) are provided and must be copied into the respective task directories.

### Tasks

#### Task 0: Creating an Interface for a Student

- **Directory**: `task_0`
- **Files**: `task_0/js/main.ts`, `task_0/package.json`, `task_0/.eslintrc.js`, `task_0/tsconfig.json`, `task_0/webpack.config.js`
- **Description**: Create a `Student` interface and render a table of student data using vanilla JavaScript and TypeScript.

#### Task 1: Building a Teacher Interface

- **Directory**: `task_1`
- **Files**: `task_1/js/main.ts`, `task_1/webpack.config.js`, `task_1/tsconfig.json`, `task_1/package.json`
- **Description**: Create a `Teacher` interface with various attributes, and extend it in subsequent tasks.

#### Task 2: Extending the Teacher Class

- **Directory**: `task_1`
- **Files**: `task_1/js/main.ts`
- **Description**: Extend the `Teacher` interface to create a `Directors` interface.

#### Task 3: Printing Teachers

- **Directory**: `task_1`
- **Files**: `task_1/js/main.ts`
- **Description**: Write a function `printTeacher` and an interface for the function.

#### Task 4: Writing a Class

- **Directory**: `task_1`
- **Files**: `task_1/js/main.ts`
- **Description**: Write a `StudentClass` class with specific methods and an interface for the class.

#### Task 5: Advanced Types Part 1

- **Directory**: `task_2`
- **Files**: `task_2/js/main.ts`, `task_2/webpack.config.js`, `task_2/tsconfig.json`, `task_2/package.json`
- **Description**: Create interfaces for `Director` and `Teacher` with specific methods and implement these interfaces in classes.

#### Task 6: Creating Functions Specific to Employees

- **Directory**: `task_2`
- **Files**: `task_2/js/main.ts`
- **Description**: Write functions `isDirector` and `executeWork` to determine the type of employee and execute their tasks.

#### Task 7: String Literal Types

- **Directory**: `task_2`
- **Files**: `task_2/js/main.ts`
- **Description**: Create a string literal type `Subjects` and a function `teachClass`.

#### Task 8: Ambient Namespaces

- **Directory**: `task_3`
- **Files**: `task_3/js/main.ts`, `task_3/js/interface.ts`, `task_3/js/crud.d.ts`, `task_3/package.json`, `task_3/tsconfig.json`, `task_3/webpack.config.js`
- **Description**: Create an interface and type, use a third-party library, and write an ambient declaration file.

#### Task 9: Namespace & Declaration Merging

- **Directory**: `task_4`
- **Files**: `task_4/js/subjects/Cpp.ts`, `task_4/js/subjects/Java.ts`, `task_4/js/subjects/React.ts`, `task_4/js/subjects/Subject.ts`, `task_4/js/subjects/Teacher.ts`, `task_4/package.json`, `task_4/tsconfig.json`
- **Description**: Create a namespace and merge declarations for a `Teacher` interface and several `Subject` classes.

#### Task 10: Update Main File

- **Directory**: `task_4`
- **Files**: `task_4/js/main.ts`
- **Description**: Create and export constants for `Cpp`, `Java`, and `React` subjects, and a `Teacher` object with specific experience.

#### Task 11: Brand Convention & Nominal Typing

- **Directory**: `task_5`
- **Files**: `task_5/js/main.ts`, `task_5/package.json`, `task_5/webpack.config.js`, `task_5/tsconfig.json`
- **Description**: Create interfaces `MajorCredits` and `MinorCredits` and functions to sum credits.

## Getting Started

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/alx-backend-javascript.git
    cd alx-backend-javascript/0x04-TypeScript
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

3. **Run tasks**:
    - Each task directory contains its own `package.json` and configuration files.
    - Navigate to the task directory and run the build/test commands.

4. **Build the project**:
    ```bash
    npm run build
    ```

5. **Run tests**:
    ```bash
    npm test
    ```

## Contribution

Feel free to fork the repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

By completing these tasks, you'll gain a solid understanding of TypeScript and its application in real-world scenarios. Happy coding!

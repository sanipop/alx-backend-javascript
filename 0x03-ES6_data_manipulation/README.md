# 0x03. ES6 Data Manipulation

## Description

This project focuses on using ES6 features for data manipulation in JavaScript. You'll learn about arrays, typed arrays, and various data structures such as Set, Map, and WeakMap. The project involves creating and manipulating lists of students, groceries, and other items using modern JavaScript methods like `map`, `filter`, and `reduce`.

## Learning Objectives

By the end of this project, you should be able to:

- Use `map`, `filter`, and `reduce` on arrays.
- Understand and use typed arrays.
- Utilize the Set, Map, and WeakMap data structures effectively.

## Requirements

- All files will be executed on Ubuntu 18.04 LTS using NodeJS 12.11.x.
- Allowed editors: `vi`, `vim`, `emacs`, `Visual Studio Code`.
- All files should end with a new line.
- A `README.md` file at the root of the project folder is mandatory.
- Your code should use the `.js` extension.
- Your code will be tested using Jest and the command `npm run test`.
- Your code will be verified against lint using ESLint.
- Your code needs to pass all the tests and lint checks. You can verify the entire project by running `npm run full-test`.
- All of your functions must be exported.

## Setup

### Install NodeJS 12.11.x

Run the following commands to install NodeJS 12.11.x:

```sh
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt install nodejs -y
nodejs -v  # should output v12.11.1
npm -v  # should output 6.11.3
```

### Install Jest, Babel, and ESLint

In your project directory, use the supplied `package.json` and run:

```sh
npm install
```

### Configuration Files

Add the following configuration files to your project directory:

- `package.json`
- `babel.config.js`
- `.eslintrc.js`

Don’t forget to run `npm install` after adding the `package.json`.

## Tasks

### 0. Basic list of objects

Create a function named `getListStudents` that returns an array of objects.

```javascript
// 0-get_list_students.js
export default function getListStudents() {
  return [
    { id: 1, firstName: 'Guillaume', location: 'San Francisco' },
    { id: 2, firstName: 'James', location: 'Columbia' },
    { id: 5, firstName: 'Serena', location: 'San Francisco' }
  ];
}
```

### 1. More mapping

Create a function `getListStudentIds` that returns an array of ids from a list of objects.

```javascript
// 1-get_list_student_ids.js
export default function getListStudentIds(arr) {
  if (!Array.isArray(arr)) return [];
  return arr.map(student => student.id);
}
```

### 2. Filter

Create a function `getStudentsByLocation` that returns an array of objects located in a specific city.

```javascript
// 2-get_students_by_loc.js
export default function getStudentsByLocation(students, city) {
  return students.filter(student => student.location === city);
}
```

### 3. Reduce

Create a function `getStudentIdsSum` that returns the sum of all the student ids.

```javascript
// 3-get_ids_sum.js
export default function getStudentIdsSum(students) {
  return students.reduce((sum, student) => sum + student.id, 0);
}
```

### 4. Combine

Create a function `updateStudentGradeByCity` that returns an array of students for a specific city with their new grades.

```javascript
// 4-update_grade_by_city.js
export default function updateStudentGradeByCity(students, city, newGrades) {
  return students
    .filter(student => student.location === city)
    .map(student => {
      const gradeObj = newGrades.find(grade => grade.studentId === student.id);
      return { ...student, grade: gradeObj ? gradeObj.grade : 'N/A' };
    });
}
```

### 5. Typed Arrays

Create a function named `createInt8TypedArray` that returns a new ArrayBuffer with an Int8 value at a specific position.

```javascript
// 5-typed_arrays.js
export default function createInt8TypedArray(length, position, value) {
  const buffer = new ArrayBuffer(length);
  const view = new DataView(buffer);
  if (position >= length) {
    throw new Error('Position outside range');
  }
  view.setInt8(position, value);
  return view;
}
```

### 6. Set data structure

Create a function named `setFromArray` that returns a Set from an array.

```javascript
// 6-set.js
export default function setFromArray(arr) {
  return new Set(arr);
}
```

### 7. More set data structure

Create a function named `hasValuesFromArray` that returns a boolean if all the elements in the array exist within the set.

```javascript
// 7-has_array_values.js
export default function hasValuesFromArray(set, arr) {
  return arr.every(value => set.has(value));
}
```

### 8. Clean set

Create a function named `cleanSet` that returns a string of all the set values that start with a specific string.

```javascript
// 8-clean_set.js
export default function cleanSet(set, startString) {
  if (!startString || !startString.length) return '';
  const filteredValues = [...set].filter(value => value.startsWith(startString));
  return filteredValues.map(value => value.slice(startString.length)).join('-');
}
```

### 9. Map data structure

Create a function named `groceriesList` that returns a map of groceries with the specified items.

```javascript
// 9-groceries_list.js
export default function groceriesList() {
  const groceries = new Map();
  groceries.set('Apples', 10);
  groceries.set('Tomatoes', 10);
  groceries.set('Pasta', 1);
  groceries.set('Rice', 1);
  groceries.set('Banana', 5);
  return groceries;
}
```

### 10. More map data structure

Create a function named `updateUniqueItems` that updates the map for all items with initial quantity of 1.

```javascript
// 10-update_uniq_items.js
export default function updateUniqueItems(map) {
  if (!(map instanceof Map)) {
    throw new Error('Cannot process');
  }
  map.forEach((value, key) => {
    if (value === 1) {
      map.set(key, 100);
    }
  });
}
```

### 11. Weak link data structure (Advanced)

Export a const instance of WeakMap and name it `weakMap`.

Export a new function named `queryAPI` to track the number of times it is called for each endpoint.

```javascript
// 100-weak.js
export const weakMap = new WeakMap();

export function queryAPI(endpoint) {
  if (!weakMap.has(endpoint)) {
    weakMap.set(endpoint, 0);
  }
  const count = weakMap.get(endpoint) + 1;
  weakMap.set(endpoint, count);

  if (count >= 5) {
    throw new Error('Endpoint load is high');
  }
}
```

## Repository

- GitHub repository: [alx-backend-javascript](https://github.com/sanipop/alx-backend-javascript)
- Directory: `0x03-ES6_data_manipulation`

## Author

This project was created by Abdulmalik Sani. If you have any questions, feel free to contact me at thepersian82@gmail.com.

# Project: alx-backend-javascript

## Setup

### Install NodeJS 12.11.x
To set up the project, first install NodeJS version 12.11.x. You can do this using the following commands in your home directory:

```sh
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt install nodejs -y
```

Verify the installation:

```sh
nodejs -v
# v12.11.1

npm -v
# 6.11.3
```

### Install Jest, Babel, and ESLint
In your project directory, install Jest, Babel, and ESLint by using the supplied `package.json` and running `npm install`.

### Configuration Files
Add the following files to your project directory:

#### `package.json`
*(Click to show/hide file contents)*

#### `babel.config.js`
*(Click to show/hide file contents)*

#### `.eslintrc.js`
*(Click to show/hide file contents)*

Don't forget to run `npm install` once you have the `package.json` file.

## Tasks

### Task 0: You used to attend a place like this at some point
Implement a class named `ClassRoom`:

- Prototype: `export default class ClassRoom`
- Accepts one attribute named `maxStudentsSize` (Number) and assigns it to `_maxStudentsSize`.

Example:
```js
import ClassRoom from "./0-classroom.js";

const room = new ClassRoom(10);
console.log(room._maxStudentsSize); // 10
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `0-classroom.js`

### Task 1: Let's make some classrooms
Import the `ClassRoom` class from `0-classroom.js` and implement a function named `initializeRooms`. It should return an array of 3 `ClassRoom` objects with sizes 19, 20, and 34.

Example:
```js
import initializeRooms from './1-make_classrooms.js';
console.log(initializeRooms());
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `1-make_classrooms.js`

### Task 2: A Course, Getters, and Setters
Implement a class named `HolbertonCourse` with attributes `name` (String), `length` (Number), and `students` (array of Strings). Verify the types during object creation. Each attribute should be stored in an “underscore” version (e.g., `_name`). Implement getters and setters for each attribute.

Example:
```js
import HolbertonCourse from "./2-hbtn_course.js";

const c1 = new HolbertonCourse("ES6", 1, ["Bob", "Jane"]);
console.log(c1.name); // ES6
c1.name = "Python 101";
console.log(c1); // { _name: 'Python 101', _length: 1, _students: [ 'Bob', 'Jane' ] }
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `2-hbtn_course.js`

### Task 3: Methods, static methods, computed methods names..... MONEY
Implement a class named `Currency` with attributes `code` (String) and `name` (String). Store each attribute in an “underscore” version (e.g., `_name`). Implement getters and setters for each attribute and a method named `displayFullCurrency` that returns `name (code)`.

Example:
```js
import Currency from "./3-currency.js";

const dollar = new Currency('$', 'Dollars');
console.log(dollar.displayFullCurrency()); // Dollars ($)
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `3-currency.js`

### Task 4: Pricing
Import the `Currency` class from `3-currency.js` and implement a class named `Pricing` with attributes `amount` (Number) and `currency` (Currency). Store each attribute in an “underscore” version (e.g., `_name`). Implement getters and setters for each attribute. Implement a method named `displayFullPrice` that returns `amount currency_name (currency_code)` and a static method `convertPrice` that accepts `amount` and `conversionRate` and returns the converted amount.

Example:
```js
import Pricing from './4-pricing.js';
import Currency from './3-currency.js';

const p = new Pricing(100, new Currency("EUR", "Euro"));
console.log(p);
console.log(p.displayFullPrice()); // 100 Euro (EUR)
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `4-pricing.js`

### Task 5: A Building
Implement a class named `Building` with attribute `sqft` (Number). Store each attribute in an “underscore” version (e.g., `_sqft`). Implement a getter for each attribute. This class should be considered abstract, and any class extending it should implement a method named `evacuationWarningMessage`. If not implemented, throw an error with the message `Class extending Building must override evacuationWarningMessage`.

Example:
```js
import Building from './5-building.js';

const b = new Building(100);
console.log(b);

class TestBuilding extends Building {}

try {
    new TestBuilding(200);
} catch(err) {
    console.log(err); // Error: Class extending Building must override evacuationWarningMessage
}
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `5-building.js`

### Task 6: Inheritance
Import `Building` from `5-building.js` and implement a class named `SkyHighBuilding` that extends `Building` with attributes `sqft` (Number) and `floors` (Number). Store each attribute in an “underscore” version (e.g., `_floors`). Implement a getter for each attribute and override the `evacuationWarningMessage` method to return `Evacuate slowly the NUMBER_OF_FLOORS floors.`.

Example:
```js
import SkyHighBuilding from './6-sky_high.js';

const building = new SkyHighBuilding(140, 60);
console.log(building.sqft); // 140
console.log(building.floors); // 60
console.log(building.evacuationWarningMessage()); // Evacuate slowly the 60 floors
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `6-sky_high.js`

### Task 7: Airport
Implement a class named `Airport` with attributes `name` (String) and `code` (String). Store each attribute in an “underscore” version (e.g., `_code`). The default string description of the class should return the airport code.

Example:
```js
import Airport from "./7-airport.js";

const airportSF = new Airport('San Francisco Airport', 'SFO');
console.log(airportSF); // Airport { _name: 'San Francisco Airport', _code: 'SFO' }
console.log(airportSF.toString()); // [object SFO]
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `7-airport.js`

### Task 8: Primitive - Holberton Class
Implement a class named `HolbertonClass` with attributes `size` (Number) and `location` (String). Store each attribute in an “underscore” version (e.g., `_size`). When the class is cast into a Number, it should return the size. When the class is cast into a String, it should return the location.

Example:
```js
import HolbertonClass from "./8-hbtn_class.js";

const hc = new HolbertonClass(12, "Mezzanine");
console.log(Number(hc)); // 12
console.log(String(hc)); // Mezzanine
```

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `8-hbtn_class.js`

### Task 9: Hoisting
Fix the provided code to make it work. Ensure the classes are properly defined before they are instantiated.

Repository:
- GitHub: `alx-backend-javascript`
- Directory: `0x02-ES6_classes`
- File: `9-hoisting.js`

### Task 10: Vroom
Implement a class named `Car` with attributes `brand` (String), `motor` (String), and `color` (String). Store each attribute in an “underscore” version (e.g., `_brand`). Add a method named `cloneCar` that returns a new object of the class.

Example:
```js
import Car from "./10-car.js";

class TestCar extends Car {}

const tc1 = new TestCar("Nissan", "Turbo", "Pink");
const tc2 = tc1.cloneCar();

console.log(tc1); // TestCar { _brand: 'Nissan', _motor: 'Turbo', _color: 'Pink' }
console.log(tc1 instanceof TestCar); // true
console.log(tc2); // TestCar { _brand: undefined, _motor: undefined, _color

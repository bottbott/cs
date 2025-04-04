## Arrays

#### Iteration methods

#### reduce

#### map

#### filter

#### some

Some returns true if at least one element in the array passes the test implemented by the provided function.

```javascript
const numbers = [1, 2, 3, 4, 5];
const hasEven = numbers.some((number) => number % 2 === 0);
console.log(hasEven); // true
```

### splice

## Operators

### ? optional chaining

If the method or property accessed does not exist, then `null` or `undefined` is returned instead of throwing an error.

```js
const person = {
  name: "John",
  age: 30,
};

const city = person.address.city; // Error: Cannot read property 'city' of undefined

const city = person.address?.city; // null
```

### ... spread

The spread operator takes an iterator (such as a string or array), and lets us expand it into individual elements where we can use it in a function that expects zero or more arguments, or where elements are expected.

```javascript
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];
console.log(newNumbers); // [1, 2, 3, 4]
```

### Destructuring

Destructuring allows us to extract multiple properties from an object or multiple elements from an array and assign them to variables.

```javascript
const person = {
  name: "John",
  age: 30,
  city: undefined,
};

const { name, age, city = "New York" } = person; // city is undefined, so we can set a default value
console.log(name, age); // John 30
```

```javascript
const numbers = [1, 2, 3];
const [a, b, c] = numbers;
console.log(a, b, c); // 1 2 3
```

# Arrays

<details><summary>What is an array?</summary>

  An array is a built-in data structure that we can use to store a collection of related data. It is an ordered list of values where each value is called an element specified by an index.
</details>

<details><summary>How do you create an array?</summary>

  We use square brackets to enclose the data, and separate the values with commas.

```javascript
let arr = [11, 22, 33, 44, 55];
```

The values of an array are sometimes referred to as elements. They can be of any data type - even other arrays!

```javascript
let names = [
    ['Ava', 'Amelia', 'Avery'],
    ['Brooke', 'Bella'],
    ['Charlotte', 'Chloe', 'Camilla', 'Claire']
];

console.log(names[1]);  // ["Brooke", "Bella"]
console.log(names[1][0]);  // "Brooke"
```

</details>

<details><summary>How do we access elements of an array?</summary>
  
With the indeces. Each element of an array has an associated index. Indeces are integers starting at zero (0). We enclose the index in square brackets and "provide it" to the array.

```javascript
let arr = [11, 22, 33, 44, 55];
console.log(arr[0]);  // 11
console.log(arr[1]);  // 22
```

</details>

<details><summary>How would we print out the last value of any given array?</summary>
  
By using its `length` property. Arrays have a property called `.length` which represents the number of values inside the array. Since indeces start at 0, the last element is always located at the index `[array].length - 1`.

```javascript
let arr = [11, 22, 33, 44, 55];
console.log(arr[arr.length - 1]);  // 55
```

</details>

<details><summary>How would we iterate any given array?</summary>
One of the most common things we want to do with an array is iterate over it so that we can look at and use each element in an array. We commonly use a `for` loop to iterate over an array.

Imagine that we want to iterate through every element of our array from the first index to the last index. To achieve this goal, we essentially define a four-step process:

1. Declare a variable that represents the first index (`i`) and set its value to the first index (`0`).
2. Write a conditional statement that terminates the `for` loop when we have iterated once for each element in the array.
3. Increment `i` after each iteration of the `for` loop.
4. During each iteration, we use `i` to access an element in the array.

For example, let's look at this code that iterates over all the elements of a string array called _books_:

```javascript
let books = ["JavaScript: The Good Parts", "Eloquent JS", "You Don't Know JS"];

for (let i = 0; i < books.length; i++) {
    let book = books[i];
    console.log(book);
}
```

This will output:

```txt
JavaScript: The Good Parts
Eloquent JS
You Don't Know JS
```

In this example, `i` starts at `0`. Since `i < books.length` is `true`, the statement of the loop runs. In the first iteration of the loop, `book` is set to `books[0]` which is `JavaScript: The Good Parts`.

Then `i` is incremented to `1` due to the `i++` statement in the `for` loop definition. The condition `i < books.length` is checked and in this iteration of the loop, `1 < 3` evaluates to `true`. Since the condition of the `for` loop is true, the next statement runs where `i` is `1`.

This loop continues until the condition is `false`. In this case, that happens when `i` becomes `3` which works out perfectly, as `books[3]` is out of index for the `books` array.

One important thing to note here is the use of `<` instead of `<=` in the condition when referring to the length of the array. The length of an array will always be one more than the last index since arrays begin with the index of `0`. For example, for an array with 5 items in it, the last index would be `4`. 

To avoid trying to access an index of an array that is out of range, the condition `i < arr.length` is typically used when iterating through arrays.

Let's look at another example of using a for loop to iterates over all the elements of an array called numbers:

```javascript
const numbers = [10, 20, 30];

for (let i=0; i<numbers.length; i++) {
  console.log(numbers[i]);
}
// 10
// 20
// 30
```

This code will iterate through all the elements in the array called numbers and print them out to the console. 

Extra ways to loop through an array:
- For Of loops with Arrays (covered in next section).
- [For In loops with Arrays](https://www.w3schools.com/js/js_loop_forin.asp)
- [ForEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
</details>

<details><summary>How would we iterate over an array using a For Of loop?</summary>

Let's look at this code that iterates over all the elements of an array called numbers:

```javascript
const numbers = [10, 20, 30];

for (let number of numbers) {
  console.log(number);
}
// 10
// 20
// 30
```
In the above program, the for...of loop is used to iterate over the numbers array object and display all its values. In plain English, you can read the above code as: for every number in the numbers array, print out the number. 

Question: Would the code still work the same way if we change the word `number` to `item`?

```javascript
const numbers = [10, 20, 30];

for (let item of numbers) {
  console.log(item);
}

```

For more information on for of loops, please take a look at the [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of).

</details>


## Array Methods

### [Push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

The `push` method adds an element to the end of the array and will return the new length. It will take any number of arguments and add all of them to the array. This item can also be **another array!** However, it does not merge the arrays, instead, it adds the array as an item within the targeted array.

```js
let myArr = [1, 2, 3];
let newLength = myArr.push(4);
console.log(myArr);         // Outputs [ 1, 2, 3, 4 ]
console.log(newLength);     // Outputs 4
console.log(myArr.length);  // Outputs 4
myArr.push(5, 6, 7);
console.log(myArr);         // Outputs [ 1, 2, 3, 4, 5, 6, 7 ]
console.log(newLength);     // Outputs 4
console.log(myArr.length);  // Outputs 7
myArr.push([ 8, 9, 10 ]);
console.log(myArr);         // Outputs [ 1, 2, 3, 4, 5, 6, 7, [8 , 9, 10 ] ]
console.log(myArr.length);  // Outputs 8
```
---

### [Pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)

The `pop` method will remove the last item in the array. It takes no arguments and returns the item removed from the array. Even though `pop` takes no arguments, it is still a method and needs to be invoked. Therefore, it needs `()`.

```js
let myArr = [1, 2, 3];
let removed = myArr.pop();
console.log(myArr);    // Outputs [ 1, 2 ]
console.log(removed);  // Outputs 3
```
---

### [Shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)

The `shift` method removes and returns the first element of the array. This is the same thing as `pop` but at the front of the array.

```js
let myArr = [1, 2, 3];
let removed = myArr.shift();
console.log(myArr);    // Output [ 2, 3 ]
console.log(removed);  // Output 1
```
---

### [Unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)

The `unshift` method adds an item to the beginning of the array. This is the same as `push` but does so at the front of the array. This method returns the new length of the array.

```js
let myArr = [1, 2, 3];
let newLength = myArr.unshift(0);
console.log(myArr);      // Output [ 0, 1, 2, 3 ]
console.log(newLength);  // Output 4
```
---

### [Slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

The `slice` method will return a shallow copy of a portion of a given array. A shallow copy means that if one of the items in the array being copied is another array or an object, that inner array/object will not be duplicated, but instead, the reference will remain the same as in the original array. We will take a deeper dive into [references](05-reference-types.md) later on this module.

This method takes two parameters, the index of the start of the slice, followed by the index of the end of the slice. The end slice goes up to but not including the end index value. If only one argument is provided, the slice will start at the given argument and go to the end of the array.

Note: slice does not alter the original array!

```js
let myArr = [1, 2, 3];
let slice1 = myArr.slice(1);
let slice2 = myArr.slice(1, 2);
console.log(myArr);   // Outputs [ 1, 2, 3 ]
console.log(slice1);  // Outputs [ 2, 3 ]
console.log(slice2);  // Outputs [ 2 ]
```
---

### [Splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

The `splice` method is similar to `slice` except that it also alters the original array. This method typically takes two arguments. The first is where to start the `splice`, and the second is how many items you want to remove and "splice" out of the array. If the second argument is omitted, the splice will go to the end of the array.

```js
let myArr1 = [1, 2, 3];
let myArr2 = [1, 2, 3];
let splice1 = myArr1.splice(1);
let splice2 = myArr2.splice(1, 1);
console.log(myArr1);   // Outputs [ 1 ]
console.log(myArr2);   // Outputs [ 1, 3 ]
console.log(splice1);  // Outputs [ 2, 3 ]
console.log(splice2);  // Outputs [ 2 ]
```
---

### [indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)

The `indexOf` method returns the first index at which a certain item is found. If the item is not found, indexOf returns `-1`.

```js
let myArr = [1, 2, 3, 2];
let indexOf2 = myArr.indexOf(2);
let indexOf3 = myArr.indexOf(3);
let indexOf4 = myArr.indexOf(4);
console.log(indexOf2);  // Outputs 1
console.log(indexOf3);  // Outputs 2
console.log(indexOf4);  // Outputs -1
```
---

## Higher Order Array Methods

### [Mapping](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

The `map` method creates a new array populated with the results of calling a provided function on every element in the calling array and will return a new array with each element being the result of the callback function. It will take a callback function as an argument, which can have multiple parameters within it.

The following code takes an array of numbers and creates a new array containing the square roots of the numbers in the first array:

```js
const numbers = [1, 4, 9];
const roots = numbers.map((num) => Math.sqrt(num));

// roots array is now [1, 2, 3]
// numbers array is still [1, 4, 9]

```
---

### [Filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

The `filter` method creates a shallow copy of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the callback function. It will take a callback function as an argument, which can have multiple parameters within it.

The following example returns all prime numbers in the array:

```js
const array = [-3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13];

function isPrime(num) {
  for (let i = 2; num > i; i++) {
    if (num % i === 0) {
      return false;
    }
  }
  return num > 1;
}

console.log(array.filter(isPrime)); // [2, 3, 5, 7, 11, 13]

```
---


### [Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

The `reduce` method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

The following code takes an array of numbers and returns the sum of all the elements in the array:

```js
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce( (accumulator, currentValue) => accumulator + currentValue, initialValue);

console.log(sumWithInitial);
// Expected output: 10

```
---


### [Find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

The `find` method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

The following code takes an array of numbers and finds the first instance where the element has a value greater than 10:

```js
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// Expected output: 12

```
---

### [Find Index](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)

The `findIndex` method is very similar to the `find` method discussed above, with one caveat. Instead of returning the actual element, the `findIndex` method returns the index of the first element in an array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned. 

The following code takes an array of numbers and finds the index of the first instance where the element has a value greater than 10:

```js
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// Expected output: 1

```
---


# Objects

In JavaScript, an object represents a standalone entity with properties. For example, a shirt can have distinct properties such as color, brand, sleeve length, size, etc. This can be applied to JavaScript Objects as well. They have properties that define their characteristics.

Objects can contain multiple values and are organized via `key: value` pairs. Let's begin by exploring basic Object creation.

## Key-value pairs

We're going to declare a variable named `person` and set it to an empty **object literal**:

```javascript
let person = {};
```

Objects start with an open curly brace and end with a closing curly brace. Inside of these braces, we store data as **key-value pairs**.

Here's an example of an object literal with one key-value pair. In this case, the key is `firstName` and the value associated with it is `"Bruce"`.

```javascript
let person = {
  firstName: 'Bruce'
};
```

The key-value pair is separated with a colon. The key is written _with or without quotes_, and the value is written as a desired data type, such as the string `"Bruce"`. Keys without quotes are restricted to _valid JavaScript variable names_.

If we store more than one key-value pair, each pair must be separated with a comma. The value of the key-value pairs, as you'll notice, can have a value type of either primitive or reference.

<details>
<summary>Note regarding <code>favoriteColors</code></summary>
<br>

>  The `favoriteColors` key in the object below is an Array. Arrays are used to hold many items and behave like lists. For more info on Arrays, check out the [Array Docs on MDN](https://developer.mozilla.org/en-US/docs/Glossary/Array).
</details>

```javascript
let person = {
  firstName: 'Bruce',
  lastName: 'Wayne',
  favoriteNumber: 33,
  favoriteColors: ['black', 'yellow'] //This is an array 
};
```

### Dot notation vs. square bracket notation

Imagine that we declared a variable named `cat` and assigned it an empty object literal. How do we add key-value pairs to `cat`? We have two options: dot notation and square bracket notation.

Dot notation works the following way:

```javascript
let cat = {};
cat.firstName = 'Felix';
cat.lastName = 'The Cat';

console.log(cat);
// {firstName: "Felix", lastName: "The Cat"}
```

When using dot notation, the keys are placed after the dot. The corresponding values of the keys become the right operand of the equality operator.


## Accessing Objects

### Dot notation vs. square bracket notation

To read the value of a key-value pair, we need to use dot notation or square bracket notation:

```javascript
const cat = {
  firstName: 'Felix',
  lastName: 'The Cat'
};

console.log(cat.firstName); // "Felix"
console.log(cat['firstName']); // "Felix"

console.log(cat.lastName); // "The Cat"
console.log(cat['lastName']); // "The Cat"
```

Notice that we had to use _quotation marks_ with the square bracket notation. If we didn't include the quotation marks, the JavaScript interpreter would mistake `firstName` and `lastName` to be variables instead of keys. An example will help elaborate this point:

```javascript
const cat = {
  firstName: 'Felix', // this is the firstName key with the value of "Felix"
  lastName: 'The Cat'
};

const firstName = 'Boooo'; // this is the firstName variable with the value of "Booo"

console.log(cat.firstName); // "Felix"
console.log(cat['firstName']); // "Felix"
console.log(cat[firstName]); // undefined (notice the lack of quotes, analogous to cat["Boooo"])

const foo = 'firstName';
console.log(cat.foo); // undefined (analogous to cat["foo"], cat doesn't have a key "foo")
console.log(cat['foo']); // undefined
console.log(cat[foo]); // "Felix"
```

### Updating key-value pairs

We can update an existing key's value using dot notation or square bracket notation.

```javascript
const cat = {
  firstName: 'Felix',
  lastName: 'The Cat'
};

console.log(cat); // {firstName: 'Felix', lastName: 'The Cat'}

cat.firstName = 'Fritz'; // reassignment with dot notation
cat['lastName'] = 'The Other Cat'; // reassignment with square bracket notation

console.log(cat); // {firstName: 'Fritz', lastName: 'The Other Cat'}
```

## Methods

Objects can hold any data type in a `key:value` pair format. The value can even be a function! When a function is in an object, it is called a `method`.

```js
let person = {
    name: "Jack Bauer",
    hours: 24,
    getFullName: function () {
        console.log(this.name) // person object contains printName() method
    }
}

person.getFullName() // invokes method, prints "Jack Bauer"
```

In the given example, the object named `person` has `name` and `hours` properties and a `method` called `getFullName`. This method is accessed like any other property either via dot notation or square bracket notation. The method is invoked just like any other function by using `()`. 

Note again the use of `this` in the method code to access properties from within the object.

### Method Parameters

Just like a regular function, methods can use parameters too.

```js
let person = {
    firstName: "Jack",
    lastName: "Bauer",
    hours: 24,
    getFullName: function (isLastNameFirst) {
      if(isLastNameFirst) {
        console.log(`${this.lastName}, ${this.firstName}`)
      } else {
        console.log(`${this.firstName} ${this.lastName}`)
      }
    }
}

person.getFullName(false) // invokes method, prints "Jack Bauer"
person.getFullName(true) // invokes method, prints "Bauer, Jack"
```

# Iterating over Objects

A `for-in` loop allows you to iterate over each key in an object. Here's the syntax for a `for-in` loop:

```javascript
for (variable in object) statement;
```

Imagine that we want to iterate through every key-value pair in an object named `person`. To achieve this goal, we define a two-step process:

1. Declare a variable that represents the key (`key` in the example below), and associate it with an object using the keyword `in`.
2. Use that variable (`key`) to access the keys, or provide it to the name of the object to get the values (`person[key]`). Note that `key` here is not in quotes because it is a variable name.

```javascript
const person = {
  firstName: 'Homer',
  middleName: 'Jay',
  lastName: 'Simpson'
};

for (const key in person) {
  console.log(key); // prints out the keys
}
// "firstName"
// "middleName"
// "lastName"

for (const key in person) {
  console.log(person[key]); // prints out the values
}
// "Homer"
// "Jay"
// "Simpson"
```

Note that "key" is not a keyword. It is only a variable name. It can be substituted with any valid variable name as shown [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in).
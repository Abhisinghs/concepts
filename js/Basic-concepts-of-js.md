# Initial Concepts to cover in JS
Welcome developers. In this blog, we will understand the basic 
concepts of JavaScript. I hope you will like most this blog because I have covered point-to-point
concepts instead of writing theory.

let's start...
## What are data types in Javascript?
In every programming language, define the types of data that a variable can store. Data types can be divided into two parts 
* Primitive data types
* Non-primitive data types

### **1.Primitive data types:**
All types except objects are called primitive data types. Primitive data type includes 
* Number
* string
* boolean
* undefined
* null
* symbol
* BigInt

**Note:** You do not remember the specific variable type for a particular value because javascript has only three variables and you can assign any type of value in variable unlike other programming languages.

### Number
It represent a number and can be written with or without decimal. 
```bash
let num_without_decimal = 2;
let num_with_decimal = 2.3;
```

### String
It represents the textual data and is written with quotes. A string can be represented using single and double quotes.
```bash
let str_with_single_quote = 'Hello developers'          //single quote  
let str_with_double_quote = "I love javascript"         //double quote
```
### Boolean 
It represents the logical entity and has two values: true and false. It is generally used for conditional testing.
```bash
let is_boolen_type = true;         //declare boolean variable

let num_one = 2;
let num_two = 3;
console.log((num_one == num_two));      // return false
```
Output:

```bash
false
                                                                                 
```
### Undefined 
When we declare any variable and do not assign a value then the value is undefined and its type is also undefined.
```bash
let name;          //value of name is undefined 
let age = undefined;  //we can also set the value of age is undefined
console.log(name);
```
Output:
```bash
undefined
```
### Null
Null means nothing and non-existent value.
```bash
let x = null;
typeof null;           //return object 
```
### Symbol 
It is a new data type introduced in the ES6 version of JavaScript. It is used to store the unique value.
```bash
let my_symbol = Symbol('uniq_symbol');
[my_symbol]       //you can access by square brackets 
```
### BigInt 
This data type is used to store the large integers that are upper than the limitation of the number data type.  It is represented by adding “n” to an integer.
```bash
//BigInt
const x = BigInt(Number.MAX_SAFE_INTEGER); // 9007199254740991n
x + 1n === x + 2n; // false because 9007199254740992n and 9007199254740993n are unequal

//Number
Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2; // true because both are 9007199254740992
```
### typeof of primitive values 
```bash
typeof "Sundar Pichai"         // Returns "string"
typeof 3.14                    // Returns "number"
typeof true                    // Returns "boolean"
typeof 234567890123456789012345678901234567890n     // Returns bigint
typeof undefined               // Returns "undefined"
typeof null                    // Returns "object" (kind of a bug in JavaScript)
typeof Symbol('symbol')        // Returns Symbol
```
### **2.Non-primitive type:**
Primitive value stores only a single value and stores multiple and complex values so we use non-primitive type. 
* Array
* Object

**Note:** It is important to remember that any data type that is not a primitive data type, is of Object type in javascript.

## Array 
An array is the collection of data that stores multiple data values and is accessed by an index.
### Create an array
```bash
let array-one = [1, 2, 3, 4];           // literal way using square brackets 
let array-two = new Array(0);            //using new keyword
let array-three = Array.from("hello");   //create an array using iterable object 
```
### Accessing the array elements 
You can access array elements using index value and using array method also.
```bash
let arr = [1, 2, 3, 4, 5];

console.log(arr[0]);                 //using index value
arr.forEach((ele) => console.log(ele));  //using array method 
```
Output:
```bash
1
1
2
3
4
5
```
### Update the array elements 
As you know array is a non-primitive and mutable data type so you can easily modify an array.
```bash
let outdoor_games = ["Cricket", "football", "basketball", "carrom", "chess", "Hockey"]

outdoor_games[3] = "Badminton";    //update values
outdoor_games[4] = "Volleyball";
```
### Adding and removing an element
If you want to add an element from the last you can use the push-and-pop method and shift, and unshift for the front side. 
```bash
let arr = [1];

//Adding
arr.push(2);           //push element from last
arr.push(3);
console.log(arr);  // 1 2 3 

arr.unshift(0);        //put the element from front 
arr.unshift(-1);
console.log(arr);   // -1 0 1 2 3

//Removing
arr.pop();         //remove from last 
arr.shift();        //remove from front
console.log(arr);       // 0 1 2
```
Output:
```bash
[ 1, 2, 3 ]
[ -1, 0, 1, 2, 3 ]
[ 0, 1, 2 ]
```
## Object 
An object is used to store the collection of data in a key-value pair.
### Create an object?
```bash
//Object literal syntax
let obj = {};           //empty object

let car = {              // object with properties
    brand: 'Toyota',
    model: 'Camry',
    year: 2022
}

let person = new Object({name:"kalpana Chawala"});         //using new keyword

// Object constructor function
function Book(title, author) {
    this.title = title;
    this.author = author;
}

// Creating instances of the Book object
let book1 = new Book('Harry Potter', 'J.K. Rowling');
let book2 = new Book('The Great Gatsby', 'F. Scott Fitzgerald');

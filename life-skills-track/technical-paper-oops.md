# Object Oriented Programming With Real-world Example
## What is Object-oriented programming?
* Object-oriented programming is a design methodology for building the software.
* In OOPs, every logic is written to complete our work but represented as **Objects**. 
* OOP allows us to break our problems into small units of work that are represented via objects and 
their functions. We build functions around objects. So you can also know more about [OOPs](https://www.w3schools.com/cpp/cpp_oop.asp)

If you want to master anything, you must make your foundation very clear in specific skills. In the same way, to master 
the OOP concepts first, you have to understand objects. let's try to understand what is an object.

## What is an object?
Everything in the world is an entity. The entity has its property and behavior that is known as an object. This object is also called an 
instance i.e. a copy of an entity in a programming language. like - car, bike, chair, etc.

![object-img](https://static.javatpoint.com/cpp/images/oops-concept1.png)

Mention above image contains some examples of objects.
As we understand the concepts let's implement a code on how objects should be created in Javascript. 
``` bash /**
 * @Explanation
 *      Objects are instances of classes or constructors in OOP. 
 *      In JavaScript, objects are a fundamental data type, and they can store 
 *      both data (properties) and behavior (methods).
 * 
 */

// Object with properties
const Person = {
    firstName: "Sundar",
    lastName: "Pichai",
    age: 30,
    greet: function () {
        console.log(`Hello, ${this.firstName} ${this.lastName}`);
    }
};

// Accessing object properties
console.log(Person.firstName); // "Sundar"
Person.greet(); // Outputs: Hello, Sundar Pichai
```
## What is class? 
A class in OOP is a collection of objects. We call it a blueprint of how the object
should be represented. Mainly a class would consist of a name, attributes, and operations. 

``` bash

 class Student {
    constructor(firstName, lastName, id) {
        this.firstName = firstName
        this.lastName = lastName
        this.id = id
    }

    getName() {
        return this.firstName + " " + this.lastName; 
    } 

    getStudentDetail() {
        return "Student is " + this.firstName + " " + this.lastName + "\n id is " + this.id; 
    }
}

const student1 = new Student("Abhishek " , "Singh" , 1);
console.log(student1.getStudentDetail());
```

Considering the above example, the Student can be a class, that has some attributes like name and some more. 
It can have operations like getting names and student details.

## Features of OOPs
The main features of object-oriented programming are
* **Inheritance**
* **Encapsulation**
* **Abstraction**
* **Polymorphism**
  
These features make the code flexible, extensible, reusable, and easy to understand. let's discuss the features of OPPs in detail one by one.

## Inheritance
When one object acquires all the properties and behaviors of the parent object i.e. known as inheritance. It provides code reusability. 
It is used to achieve runtime polymorphism.

* Sub class - Subclass or Derived Class refers to a class that receives properties from another class.
* Super class - The term "Base Class" or "Super Class" refers to the class from which a subclass inherits its properties.
* Reusability - As a result, when we wish to create a new class, but an existing class already contains some of the code we need,
  we can generate our new class from the old class thanks to inheritance. This allows us to utilize the fields and methods of the pre-existing class.
### Types of Inheritance in javascript
**1. Prototypal Inheritance:**
* This is the core inheritance mechanism in JavaScript.
* Every object in JavaScript has a hidden property called [[Prototype]], which is a reference to another object (its prototype).

```bash
  const parentObject = {
  name: "Parent",
  greet: function() {
    console.log("Hello, I'm", ${this.name});
  }
};
const childObject = Object.create(parentObject);
childObject.name = "Child";
childObject.greet(); // Output: Hello, I'm Child

```
**2. Pseudoclassical Inheritance:**
It involves creating constructor functions and setting up the prototype chain manually to mimic the behavior of classes 
and inheritance in traditional object-oriented languages.

```bash
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log("Hello, I'm" ${this.name}`);
};

function Student(name,school) {
  Person.call(this, name);   //Call parent constructor
  this.school = school;
}

Student.prototype = Object.create(Person.prototype); //Inherit from Person
Student.prototype.constructor = Student; //Reset constructor property

const student = new Student("Alice", "Example School");
student.greet(); //Output: Hello, I'm Alice
```
**3. Functional Inheritance:**
* This approach utilizes JavaScript's first-class functions to achieve inheritance.
* It involves creating objects with shared properties and methods using factory functions or closures.
```bash
function createPerson(name) {
  return {
    name: name,
    greet: function() {
      console.log("Hello, I'm" ${this.name});
    }
  };
}

function createStudent(name, school) {
  const person = createPerson(name);
  return Object.assign(person, {
    school: school
  });
}

const student = createStudent("Bob", "Example School");
student.greet(); // Output: Hello, I'm Bob
```
## Encapsulation
Encapsulation simply means wrapping up code and data into a single unit. 
Here are two common ways to achieve encapsulation in javascript 

**1.Closures :**
Closures provide the functionality to make our variable private inside the function. Because Closure is the combination of lexical scoping 
and inner function that gives us this functionality.

```bash
function createCounter() {
  let count = 0; // Private variable

  return {
    increment: function() {
      count++;
    },
    getValue: function() {
      return count;
    }
  };
}

const counter = createCounter();
counter.increment();
console.log(counter.getValue()); // Outputs 1
console.log(counter.count); // Outputs undefined (private variable)
```
**2.Classes(ES6 and above) :**
JavaScript classes provide a more structured way to implement encapsulation using access modifiers (public, private, protected) since ES2022.
```bash
class Person {
  #name; // Private property

  constructor(name) {
    this.#name = name;
  }

  getName() {
    return this.#name;
  }

  setName(newName) {
    this.#name = newName;
  }
}

const person = new Person("Alice");
console.log(person.getName()); // Outputs "Alice"
console.log(person.#name); // Error: Private field '#name' must be declared in an enclosing class
```
## Abstraction 
An abstraction is a way of hiding the implementation details and showing only the functionality to the users. 
In other words, it ignores the irrelevant details and shows only the required ones.

let's try to achieve the abstraction in javascript
```bash
//Creating a constructor function  
 function Vehicle()  
{  
    this.vehicleName="vehicleName";  
    throw new Error("You cannot create an instance of Abstract Class");  
}  
Vehicle.prototype.display=function()  
{  
    return "Vehicle is: "+this.vehicleName;  
}  
//Creating a constructor function  
function Bike(vehicleName)  
{  
    this.vehicleName=vehicleName;  
}  
//Creating object without using the function constructor  
Bike.prototype=Object.create(Vehicle.prototype);  
var bike=new Bike("Honda");  
document.writeln(bike.display());  
```
```Output: Honda```

## Polymorphism
* Polymorphism is one of the core concepts of object-oriented programming languages where poly means many and morphism means transforming one form into another.
* Binding (or wrapping) code and data together into a single unit is known as encapsulation. 
For example: a capsule, is wrapped with different medicines.

**Features of Polymorphism:**
* Programmers can use the same method name repeatedly.
* Polymorphism has the effect of reducing the number of functionalities that can be paired together.

In this example code we will see the polymorphism with inheritance in javascript
```bash
class firstClass {
	add() {
		console.log("First Method")
	}
}
class secondClass extends firstClass {
	add() {
		console.log(30 + 40);
	}
}
class thirdClass extends secondClass {
	add() {
		console.log("Last Method")
	}
}
let ob = new firstClass();
let ob2 = new secondClass();
let ob3 = new thirdClass();
ob.add();
ob2.add();
ob3.add();
```
Outpu:
```
First Method 
70
Last Method
```
## Conclusion
* Fundamentally, the purpose of coding is to address real-world problems.
* In Object-Oriented Programming (OOP), the logic is structured around the concept of objects, incorporating key principles such as abstraction, encapsulation, inheritance, and polymorphism.
* Consider various real-world entities like cars, bikes, ATMs, and coffee machines, each with different brands and names. In OOP, these entities are referred to as objects.
* Object-Oriented Programming (OOP) improves software development by organizing code into reusable, modular components (objects and classes), promoting efficient and maintainable software design.

* ## References
* Youtube: [https://www.youtube.com/watch?v=pN-Qmv4zBcI](https://www.youtube.com/watch?v=pN-Qmv4zBcI)
* Javatpoint: [https://www.javatpoint.com/cpp-oops-concepts](https://www.javatpoint.com/cpp-oops-concepts)
* W3School: [https://www.w3schools.com/cpp/cpp_oop.asp](https://www.w3schools.com/cpp/cpp_oop.asp)

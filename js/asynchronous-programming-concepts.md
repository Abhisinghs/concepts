# Introducing asynchronous JavaScript
In this blog, we will understand the few basic asynchronous concepts of JavaScript that will help you to understand better.
we will focus on practical implementation rather than theory.

Let's start...

Before understanding the asynchronous Js first, you have to understand how javascript code is executed.
## Q1)How do Js execute the code?
JavaScript execution is a multi-step process that involves several components:

**1) Parsing:**
* The Javascript engine reads the code line by line and checks for syntax.
* If no syntax errors are found, then it creates the **Abstract Syntax Tree(AST)** which represents the code's structure.
  
**2) Compilation:**
* Modern JavaScript engines use the **Just-in-time(JIT)** compilation.
* Then it converts the Abstract Syntax Tree(AST) into the machine code(bytecode) that will computer can execute directly.
* This happens in some parts as needed.
  
**3) Execution:**
* The JavaScript engine uses the **Execution Context** to manage the execution of the code.
* An execution context is an environment where JavaScript code is executed. It defines the scope of variables, functions, and this keyword.
* There are two types of Execution context:
  
   **1.Global Execution Context:**
      Create only once when scripts start initially, it represents the global scope.

   **2.Function Execution Context:**
      Create each time when the function is called, it represents the function scope.
* Execution happens in the call stack, that follows (list in first out).
* When the function is called then a new FEC(Function Execution context) is created and pushed into the call stack.
* When the function completes, its FEC is popped off the stack, and the control returns to the calling context.

## Q2)Difference between synchronous and asynchronous code.
**synchronous code:** 
* where the execution of code is line by line.
* it is also called block code because it blocks the further execution until the above code is executed.
* Those things that are natively defined in JavaScript are the synchronous pieces of code like for-loop and log-statements.

![image](https://www.datocms-assets.com/48294/1699274913-sync-vs-async-programming-4.png?auto=format)

**asynchronous code:** 
* where the execution of code is not sequentially, it is also called the non-blocking code which means it does not stop the execution of code for asynchronous code.
* It executes the next line of code that comes after asynchronous code.
* Those functionalities provided by the runtime environment are the asynchronous piece of code like setTimout, setInterval, etc.

## Q3)Ways to convert into Async code?
* By the way, Javascript is a single-threaded language example which means a single set of tasks performed at a time.
* But we can make the javascript async in three ways-
  
**1.Callback:**
  * Callback is not an asynchronous piece of code but when we use callback inside the asynchronous code that makes the Javascript asynchronous.
  * But with the callback have many problems like readability, error handling, maintainability, etc.
  
**2.Promises:** 
* Promises are a special type of object in javascript that is used to handle the asynchronous operation in javascript.
* A promise is a readability enhancer and solves the callback hell and inversion of control problems.

**3.Async/Await:** 
* It is also a way to perform the asynchronous operation in JavaScript.
* When we simply use the async keyword before the function then it creates the asynchronous function and we easily perform the async operation inside this function.

## Q4)What is the callstack & event loop?

**Callstack:** 
  * Callstack is a place where the execution of code happens in a stacked manner (last in first out).
  * When a function is called it is pushed into the call stack and after completion of the function, it poped out from the call stack.
  * Callstack plays a very important role in executing the javascript code.

**Event-loop:**
 * Event-loop is a continuously running process that manages the execution of code in a single-threaded environment.
 * It ensures that any asynchronous operation like a timer and network request does not block the main thread execution and happens synchronously.
 * It continuously checks if the call stack is empty or not and whether the global piece of code is finished or not.
 * If the call stack is empty and a global piece of code is also done then it picks the callback function in the callback queue or macrotask queue and puts it onto the call stack to execute the callback

![image](https://media.licdn.com/dms/image/D4D12AQExWD31PDbNSQ/article-inline_image-shrink_1500_2232/0/1703925274829?e=1726704000&v=beta&t=-gIGZr58SZoZ9zhdYjkgVVk7ccXU6rAKg0lGr3evHmE)
  

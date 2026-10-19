# JavaScript (ES6) Review Questions: Topics 1–20

These questions cover the ES6 tutorial from **Topic 1 (Overview)** through **Topic 20 (New String Methods)**. They are graded from basic recall to advanced application and debugging.

---

# PART A: TOPIC 1 – ES6 OVERVIEW

## Basic

1. What does ECMAScript stand for? What organization standardizes it?
2. Name three programming languages governed by the ECMAScript specification.
3. Who developed JavaScript, and in what year?
4. What were the original names of JavaScript before it was officially named JavaScript?
5. What is the difference between ECMAScript and JavaScript?
6. List five new features introduced in ES6.
7. In which year was ECMAScript 2015 (ES6) released?
8. What was the fate of ECMAScript 4?

## Intermediate

1. Explain why ECMAScript 4 was never released. Where did its features eventually appear?
2. Match each ECMAScript version (ES5, ES5.1, ES6, ES7, ES8, ES9) with its release year.
3. Why is JavaScript described as a "client-side scripting language"?
4. What is the relationship between JavaScript, JScript, and ActionScript?

## Advanced

 1. Discuss the historical significance of ES6 compared to previous ECMAScript releases. Why is it considered a major milestone?
 2. Explain how ECMAScript standardization influences browser compatibility and modern web development.

---

# PART B: TOPIC 2 – ENVIRONMENT

## Basic

 1. What two tools do you need to write and test JavaScript/ES6 code locally?
 2. What file extension is typically used for JavaScript source files?
 3. What is Node.js? Which JavaScript engine does it use?
 4. How do you verify that Node.js is installed correctly?
 5. What is npm, and what is its purpose?
 6. Name two IDEs/editors commonly used for JavaScript development.

## Intermediate

 1. Compare Visual Studio Code and Brackets as JavaScript development environments.
 2. Why is Node.js required to run JavaScript outside a browser?
 3. What is the role of the V8 JavaScript engine?
 4. How would you open a file in the command prompt directly from VS Code?

## Advanced

 1. Explain the difference between a text editor and an IDE. When would you choose one over the other?
 2. Discuss the role of build tools and package managers (like npm) in modern JavaScript development.

---

# PART C: TOPIC 3 – SYNTAX

## Basic

 1. Name four components that make up a JavaScript program.
 2. What is a keyword? Give five examples.
 3. What is an identifier? What are its naming rules?
 4. Are JavaScript identifiers case-sensitive? Provide an example.
 5. Are semicolons required in JavaScript? Explain.
 6. How do you write a single-line comment in JavaScript? A multi-line comment?
 7. What is "strict mode"? How is it enabled?
 8. What is hoisting?
 9. Which of the following are valid identifiers: `firstName`, `first-name`, `1number`, `$price`, `_count`, `first name`? Explain why.
10. What does `"use strict"` at the top of a script do?

## Intermediate

 1. Explain the difference between declaring a variable in strict mode vs. non-strict mode.
 2. Why does the following code throw an error in strict mode but not in non-strict mode?

    ```js
    v = "Hi! I'm a strict mode script!";
    ```
 3. What happens if you place `"use strict"` inside a function? Does it affect code outside the function?
 4. Explain hoisting with an example using `var`.
 5. Why is hoisting not applicable in strict mode for certain variables?
 6. Rewrite the following snippet with proper indentation and comments:

    ```js
    function greet(){if(true){console.log("hello")}}
    ```

## Advanced

 1. Explain the "temporal dead zone" (TDZ) in relation to `let` and `const`. Why does it exist?
 2. What are the consequences of using strict mode with:
    - Undeclared variables
    - Duplicate function parameter names
    - The `with` statement
    - Assigning to read-only properties
 3. Analyze the following code and predict the output:

    ```js
    console.log(x);
    var x = 10;
    function test() {
      console.log(y);
      var y = 20;
    }
    test();
    ```
 4. Explain the difference between syntax errors and runtime errors in JavaScript.

---

# PART D: TOPIC 4 – VARIABLES

## Basic

 1. What is a variable?
 2. What are the three ways to declare a variable in ES6?
 3. What is the difference between `let` and `const`?
 4. What is dynamic typing?
 5. What is global scope? What is local (function) scope?
 6. What is block scope? Which keywords support it?
 7. What happens if you try to redeclare a `let` variable in the same block?
 8. What happens if you try to redeclare a `const` variable?
 9. Must a `const` variable be initialized at declaration?
10. Can you modify the contents of a `const` array?

## Intermediate

 1. Explain the difference between `var` and `let` with respect to block scope.
 2. Given the following code, what will be printed and why?

    ```js
    var no = 10;
    var no = 20;
    console.log(no);
    ```
 3. Given the following code, what will happen and why?

    ```js
    let no = 10;
    let no = 20;
    console.log(no);
    ```
 4. What is the output of this code? Explain.

    ```js
    var num = 10;
    function test() {
      var num = 100;
      console.log("inside: " + num);
    }
    console.log("outside: " + num);
    test();
    ```
 5. What is the output of this code?

    ```js
    var i;
    for (var i = 1; i <= 5; i++) {
      // ...
    }
    console.log(i);
    ```
 6. Rewrite the previous loop using `let`. What difference does it make?
 7. Explain why `const` does not mean the value is fully immutable.
 8. What will the following print?

    ```js
    const arr = [1, 2, 3];
    arr.push(4);
    console.log(arr);
    ```

## Advanced

 1. Predict the output:

    ```js
    let count = 100;
    for (let count = 1; count <= 3; count++) {
      console.log(count);
    }
    console.log(count);
    ```
 2. Predict the output:

    ```js
    "use strict"
    function test() {
      var num = 100;
      {
        let num = 200;
        console.log(num);
      }
      console.log(num);
    }
    test();
    ```
 3. What happens in the following code? Explain.

    ```js
    const student = { name: "Tom", age: 22 };
    student.age = 23;  // allowed?
    student = {};      // allowed?
    ```
 4. Explain the temporal dead zone with a concrete example using `let` and `const`.
 5. Why is `var` considered problematic in modern JavaScript? Give three reasons.
 6. Compare `var`, `let`, and `const` in a table covering scope, hoisting, redeclaration, reassignment, and TDZ.

---

# PART E: TOPIC 5 – OPERATORS

## Basic

 1. Define operand and operator.
 2. List the categories of operators in JavaScript.
 3. What is the difference between the `+` operator in arithmetic vs. string contexts?
 4. What does the `%` operator do?
 5. What is the difference between `++a` and `a++`?
 6. What does the ternary operator do? What is its syntax?
 7. What does `typeof` return? Give three examples.
 8. What is the spread operator? What does it do?

## Intermediate

 1. Given `a = 10, b = 5`, compute: `a + b`, `a - b`, `a * b`, `a / b`, `a % b`, `a++`, `--b`.
 2. What is a short-circuit operator? Why are `&&` and `||` called short-circuit operators?
 3. Explain the difference between `==` and `===` (though the tutorial mentions `==`, ES6 best practice favors `===`).
 4. What is the output of:

    ```js
    var a = 10;
    var result = a < 10 && a > 5;
    console.log(result);
    ```
 5. What is the difference between bitwise `&` and logical `&&`?
 6. Explain the difference between `=` and `==` (and `===`).
 7. What does the `in` operator do? Give an example.

## Advanced

 1. Predict the output:

    ```js
    var a = 2, b = 3;
    console.log(a & b);
    console.log(a | b);
    console.log(a ^ b);
    console.log(~b);
    console.log(a << b);
    console.log(a >> b);
    ```
 2. Explain how the following code works:

    ```js
    var msg = "hello" + "world";
    console.log(msg); // helloworld
    ```
 3. What is the output of:

    ```js
    var num = -2;
    var result = num > 0 ? "positive" : "non-positive";
    console.log(result);
    ```
 4. Demonstrate how the spread operator can be used to:
    - Copy an array
    - Concatenate arrays
    - Pass array values as function arguments
    - Copy an object
    - Merge two objects
 5. What does `typeof` return for each of these: `12`, `"hello"`, `true`, `undefined`, `null`, `function(){}`, `[]`, `{}`?

---

# PART F: TOPIC 6 – DECISION MAKING

## Basic

 1. List the conditional constructs in JavaScript.
 2. What is the syntax of the `if` statement?
 3. What is the syntax of the `if...else` statement?
 4. What is the `else...if` ladder used for?
 5. What is the `switch` statement? What does `break` do inside a `case`?
 6. Is the `default` block in a `switch` mandatory?

## Intermediate

1. Write a program that checks whether a number is even or odd using `if...else`.
2. Write a program that classifies a number as positive, negative, or zero using `else...if`.
3. Convert the following `if...else` chain into a `switch` statement:

    ```js
    if (grade === "A") console.log("Excellent");
    else if (grade === "B") console.log("Good");
    else if (grade === "C") console.log("Fair");
    else if (grade === "D") console.log("Poor");
    else console.log("Invalid");
    ```

100. What happens if you omit the `break` statement in a `switch` case?

## Advanced

  1. Explain "fall-through" in a `switch` statement. When might fall-through be useful?
  2. Write a program that determines the number of days in a given month (accounting for leap years) using a `switch` statement.
  3. What is the difference between `switch` and `if...else`? When would you choose one over the other?
  4. Predict the output:
    ```js
    var grade = "B";
    switch (grade) {
      case "A": console.log("Excellent");
      case "B": console.log("Good");
      case "C": console.log("Fair");
      default: console.log("Unknown");
    }
    ```

---

# PART G: TOPIC 7 – LOOPS

## Basic

  1. What is a loop? What is an iteration?
  2. What is a definite loop? Give an example.
  3. What is an indefinite loop? Give an example.
  4. What are the three parts of a `for` loop?
  5. What is the syntax of a `while` loop?
  6. What is the syntax of a `do...while` loop?
  7. What is the difference between `while` and `do...while`?
  8. What does `break` do in a loop?
  9. What does `continue` do in a loop?

## Intermediate

  1. Write a `for` loop that prints the numbers 1 to 10.
  2. Write a `while` loop that calculates the factorial of 5.
  3. Write a `do...while` loop that prints numbers from 10 to 0 in reverse.
  4. What is a `for...in` loop used for? Give an example.
  5. What is a `for...of` loop used for? Give an example.
  6. What is the difference between `for...in` and `for...of`?
  7. Write a loop that prints the first 8 Fibonacci numbers.
  8. What does the following print?
    ```js
    for (let temp, i = 0, j = 1; j < 30; temp = i, i = j, j = i + temp)
      console.log(j);
    ```

## Advanced

  1. Write a nested loop that prints a 5x5 grid of asterisks (`*`).
  2. Use a label with `break` and `continue` to control nested loops. Write an example.
  3. Explain the difference between labeled `break` and unlabeled `break` in nested loops.
  4. Write a program that finds all prime numbers between 1 and 50.
  5. Predict the output:
    ```js
    var num = 0;
    var count = 0;
    for (num = 0; num <= 20; num++) {
      if (num % 2 == 0) continue;
      count++;
    }
    console.log(count);
    ```
  6. Why is `for...of` considered more appropriate than `for...in` for iterating over arrays?

---

# PART H: TOPIC 8 – FUNCTIONS

## Basic

  1. What is a function? Why are functions useful?
  2. What is the syntax for defining a function?
  3. What is function invocation?
  4. What is a returning function? What is a parameterized function?
  5. What is a default parameter? Give an example.
  6. What is a rest parameter? How is it written?
  7. What is an anonymous function?
  8. What is a lambda/arrow function? How does it differ from a regular function?
  9. What is a generator function? How is it indicated?
 10. What is an IIFE?

## Intermediate

  1. Write a function that takes two numbers and returns their sum.
  2. Write a function with a default parameter that adds 1 to a number if no second argument is provided.
  3. Write a function using rest parameters to calculate the sum of any number of arguments.
  4. Convert the following to an arrow function:
    ```js
    var add = function(a, b) { return a + b; };
    ```
  5. What does the following output?
    ```js
    function add(a, b = 10) { return a + b; }
    console.log(add(5));
    console.log(add(5, 3));
    ```
  6. What is function hoisting? How does it differ from variable hoisting?
  7. What is the difference between a function expression and a function declaration?
  8. Write an IIFE that logs "Hello World" immediately.

## Advanced

  1. Explain the difference between `this` in a normal function vs. an arrow function.
  2. Predict the output of:
    ```js
    hoist_function();
    function hoist_function() { console.log("foo"); }
    ```
  3. Predict the output and explain:
    ```js
    hoist_function();
    var hoist_function = function() { console.log("bar"); };
    ```
  4. Write a generator that yields the colors of the rainbow.
  5. Write an infinite generator of even numbers and use it with `for...of` to print numbers up to 12.
  6. Explain the two-way communication possible with generators using `yield`.
  7. Analyze the following code and explain what happens:
    ```js
    var main = function() {
      (function() {
        for (var x = 0; x < 5; x++) {
          console.log(x);
        }
      })();
      console.log("x can not be accessed: " + x);
    };
    main();
    ```
  8. Rewrite the `Array.prototype.map()` example using an arrow function:
    ```js
    const names = ['TutorialsPoint', 'Mohtashim', 'Bhargavi', 'Raja'];
    names.map((element, index) => {
      console.log('index is ' + index + ' element value is :' + element);
    });
    ```
  9. Explain why arrow functions cannot be used as generator functions.

---

# PART I: TOPIC 9 – EVENTS

## Basic

  1. What is an event? Give three examples.
  2. What is an event handler?
  3. What does `onclick` do?
  4. What does `onsubmit` do? Where is it commonly used?
  5. What do `onmouseover` and `onmouseout` do?
  6. Name five standard HTML5 events.

## Intermediate

  1. Write an HTML page with a button that displays an alert when clicked.
  2. Write an `onsubmit` handler that validates a form before submission.
  3. Write a script that changes the background color of a `div` when the mouse hovers over it.
  4. What is the difference between `onclick` and `ondblclick`?
  5. What is `onload` used for? Give an example.

## Advanced

  1. Explain the difference between inline event handlers (e.g., `<button onclick="...">`) and event listeners added via JavaScript. Which is preferred and why?
  2. What is event bubbling? How does it affect nested elements with event handlers?
  3. Write an example where an event handler returns `false` to prevent a form from submitting.
  4. Explain `onchange` vs. `oninput`. When would you use each?
  5. How do you attach an event handler using `addEventListener()`? Compare with the older `onclick` property approach.

---

# PART J: TOPIC 10 – COOKIES

## Basic

  1. What is a cookie? Why are cookies used?
  2. What does it mean that HTTP is a stateless protocol?
  3. What are the five fields of a cookie?
  4. What happens if a cookie has no `expires` field?
  5. What is the `document.cookie` property?
  6. How do you delete a cookie?

## Intermediate

  1. Write JavaScript code to store a cookie named `"username"` with value `"John"`.
  2. Write code to read all cookies and display them.
  3. How do you set a cookie to expire one month in the future?
  4. Write code to delete a cookie named `"sessionID"`.
  5. What are the security concerns related to cookies? Mention at least two.

## Advanced

  1. Explain the `Secure` and `HttpOnly` cookie attributes. Why are they important?
  2. What is the `SameSite` attribute? What are its possible values?
  3. Explain the difference between session cookies and persistent cookies.
  4. Why should cookie values be encoded? Which function does the tutorial recommend?
  5. Explain how cookies relate to user sessions on a website.

---

# PART K: TOPIC 11 – PAGE REDIRECT

## Basic

  1. What is page redirection? Why is it used?
  2. What is the `window.location` object?
  3. What is the difference between `window.location` and `window.location.href`?
  4. What does `location.replace()` do?
  5. What does `location.assign()` do?
  6. What does `location.reload()` do?

## Intermediate

  1. Write code that redirects a user to `https://example.com` after clicking a button.
  2. What is the difference between `location.replace()` and `location.assign()`?
  3. Why should you avoid using `window.navigate()`?
  4. How does page redirection affect SEO?

## Advanced

  1. Explain why search engines do not automatically follow JavaScript-based redirects and how to fix this (mention `rel="canonical"`).
  2. What is the difference between a server-side redirect (301/302) and a client-side JavaScript redirect?
  3. Write a script that redirects to a page only if a certain condition is met (e.g., user is logged in).
  4. How can redirects be used maliciously? What are the security concerns?

---

# PART L: TOPIC 12 – DIALOG BOXES

## Basic

  1. Name three types of dialog boxes in JavaScript.
  2. What does `alert()` do?
  3. What does `confirm()` do? What are its return values?
  4. What does `prompt()` do? What are its return values?
  5. How many parameters does `prompt()` take?

## Intermediate

  1. Write code that shows an alert saying "Welcome!".
  2. Write code that asks the user for confirmation and logs the result.
  3. Write code that prompts the user for their name and greets them.
  4. What happens if the user clicks "Cancel" in a `prompt()` dialog?
  5. What is the default value parameter of `prompt()`?

## Advanced

  1. Discuss why `alert()`, `confirm()`, and `prompt()` are generally discouraged in modern web applications.
  2. What alternatives exist for creating user dialogs in modern web development?
  3. Explain how `confirm()` can be used as part of a validation flow.

---

# PART M: TOPIC 13 – VOID KEYWORD

## Basic

  1. What does the `void` keyword do?
  2. What is the return value of `void expression`?
  3. Write a `void` expression.
  4. What is `void(0)` commonly used for?

## Intermediate

  1. Explain how `void` is used with IIFEs.
  2. Why might you use `void` in a `javascript:` URI?
  3. Compare `javascript:void(0)` with `javascript:alert('hello')`.

## Advanced

  1. Explain the difference between `javascript:void(0)` and `javascript:;` (both are used in `href` attributes).
  2. What are the accessibility concerns with using `javascript:` URIs?
  3. Modern best practices suggest avoiding `javascript:` URIs. What should you use instead?

---

# PART N: TOPIC 14 – PAGE PRINTING

## Basic

  1. What does `window.print()` do?
  2. How do you trigger printing when a user clicks a button?

## Intermediate

  1. Write an HTML page with a "Print" button that prints the page.
  2. Can `window.print()` be called automatically without user interaction? What are the caveats?

## Advanced

  1. How can CSS be used to style a page specifically for printing? Mention `@media print`.
  2. Discuss the privacy and security implications of `window.print()`.

---

# PART O: TOPIC 15 – OBJECTS

## Basic

  1. What is an object in JavaScript?
  2. What is an object initializer? Give an example.
  3. What is the `Object()` constructor?
  4. What is a constructor function?
  5. What is the `Object.create()` method?
  6. What does `Object.assign()` do?
  7. How do you delete a property from an object?
  8. What does it mean that objects are reference types?

## Intermediate

  1. Create an object `person` with properties `firstName`, `lastName`, and `age`.
  2. Access the `firstName` property using dot notation and bracket notation.
  3. Write a constructor function `Car` that takes `make` and `model`.
  4. Use `Object.assign()` to merge two objects.
  5. Explain why two objects with the same properties are not `===` to each other.
  6. What is object destructuring? Give an example.
  7. Destructure properties from an object into different variable names.

## Advanced

  1. Explain ES6 shorthand property syntax. Rewrite the following:
    ```js
    var foo = 'bar';
    var baz = { foo: foo };
    ```
  2. Explain computed property names in object literals. Give an example.
  3. Explain concise method syntax. Rewrite:
    ```js
    var obj = { greet: function() { return "hello"; } };
    ```
  4. Predict the output:
    ```js
    var o1 = { a: 10 };
    var obj = Object.assign(o1);
    obj.a++;
    console.log(obj.a);
    console.log(o1.a);
    ```
  5. Explain how object destructuring handles:
    - Renaming variables
    - Default values
    - Nested objects
    - Rest properties
  6. What is the difference between cloning an object and merging objects with `Object.assign()`?

---

# PART P: TOPIC 16 – NUMBER

## Basic

  1. What are the key Number properties in JavaScript?
  2. What is `Number.EPSILON`?
  3. What is `Number.MAX_SAFE_INTEGER`? What is its value?
  4. What is the difference between `Number.MAX_VALUE` and `Number.MAX_SAFE_INTEGER`?
  5. What is `NaN`? What does it stand for?
  6. What does `Number.isNaN()` do?
  7. What does `Number.isInteger()` do?
  8. What does `Number.parseInt()` do? How does it differ from `Number.parseFloat()`?
  9. What are binary and octal literals? How do you write them in ES6?

## Intermediate

  1. Predict the output:
    ```js
    console.log(Number.isNaN(10));
    console.log(Number.isInteger(0.1));
    console.log(Number.isInteger(-100000));
    ```
  2. What does `toExponential()` do? Show with `1225.30`.
  3. What does `toFixed(2)` do to `177.234`?
  4. What does `toPrecision(2)` do to `7.123456`?
  5. Convert the number `10` to binary, octal, and hexadecimal strings.
  6. Write binary `110` and octal `15` using ES6 literal syntax.

## Advanced

  1. Explain why `NaN === NaN` returns `false`. Why does `Number.isNaN(NaN)` return `true`?
  2. Explain the difference between `Number.isNaN()` and the global `isNaN()`.
  3. Why is `Number.MAX_SAFE_INTEGER` important for safe integer operations? What happens beyond it?
  4. Explain what `Number.EPSILON` is used for in floating-point comparisons.
  5. Predict the output:
    ```js
    console.log(0.1 + 0.2 === 0.3);
    console.log(Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON);
    ```

---

# PART Q: TOPIC 17 – BOOLEAN

## Basic

  1. What is a Boolean?
  2. What are the two possible Boolean values?
  3. What is the default initial value of a Boolean object if no value is passed?
  4. What does `Boolean()` do when passed `0`, `null`, `undefined`, `""`, `NaN`?
  5. What does `Boolean()` do when passed a non-empty string or a non-zero number?

## Intermediate

  1. Predict the output:
    ```js
    var bool = new Boolean();
    console.log(bool.valueOf());
    ```
  2. What is the difference between `new Boolean(false)` and `false`? Which should you prefer?
  3. What does `boolean.toString()` return?
  4. Write code that checks whether a value is truthy or falsy using `Boolean()`.

## Advanced

  1. Explain why using `Boolean` objects (via `new Boolean()`) is discouraged in JavaScript.
  2. What does `prototype` allow you to do with Boolean objects? Give an example.
  3. Explain the concept of "truthy" and "falsy" values. List all falsy values in JavaScript.

---

# PART R: TOPIC 18 – STRINGS

## Basic

  1. What is a String object?
  2. What does `string.length` return?
  3. What does `charAt()` do? What does `charCodeAt()` do?
  4. What does `concat()` do?
  5. What does `indexOf()` do? What does `lastIndexOf()` do?
  6. What does `replace()` do?
  7. What does `slice()` do?
  8. What does `split()` do?
  9. What does `substr()` do? What does `substring()` do?
 10. What does `toLowerCase()` do? What does `toUpperCase()` do?

## Intermediate

  1. Write code that extracts "World" from `"Hello World"` using `slice()`.
  2. Write code that splits `"a,b,c"` into an array.
  3. Replace all instances of "apple" with "orange" in `"apple pie and apple juice"`.
  4. What does the following return?
    ```js
    "Hello".charAt(1);
    ```
  5. What does the following return?
    ```js
    "Hello World".indexOf("World");
    ```
  6. What does the following return?
    ```js
    "Hello".slice(1, 3);
    ```
  7. What does the following return?
    ```js
    "Hello World".split(" ");
    ```
  8. Compare `substr(start, length)` vs. `substring(start, end)`.

## Advanced

  1. Explain the difference between `indexOf()` and `lastIndexOf()` with an example.
  2. What does `localeCompare()` return? What are its possible values?
  3. Explain how `replace()` handles special replacement patterns like `$1`, `$2`, `$&`, `$``,`$'`.
  4. Predict the output:
    ```js
    var str = "Apples are round, and apples are juicy.";
    var re = /apples/gi;
    console.log(str.replace(re, "oranges"));
    ```
  5. Write a function that counts the number of vowels in a string using string methods.

---

# PART S: TOPIC 19 – SYMBOL

## Basic

  1. What is a Symbol? How does it differ from other primitive types?
  2. How do you create a Symbol?
  3. Are two symbols with the same description equal?
  4. What is `Symbol.for()`?
  5. What is `Symbol.keyFor()`?

## Intermediate

  1. Predict the output:
    ```js
    const s1 = Symbol();
    const s2 = Symbol();
    console.log(s1 === s2);
    ```
  2. Predict the output:
    ```js
    const s3 = Symbol("hello");
    const s4 = Symbol("hello");
    console.log(s3 === s4);
    ```
  3. Predict the output:
    ```js
    const userId = Symbol.for('userId');
    const user_Id = Symbol.for('userId');
    console.log(userId === user_Id);
    ```
  4. What does `Symbol.keyFor(Symbol.for("id"))` return?
  5. How do Symbols help with encapsulation in classes?

## Advanced

  1. Explain the concept of the global symbol registry.
  2. Why are Symbols immutable and unique? What purpose does this serve?
  3. Write a class with a Symbol property that can only be accessed if the caller knows the symbol.
  4. Discuss how Symbols are used in built-in JavaScript features (e.g., `Symbol.iterator`).

---

# PART T: TOPIC 20 – NEW STRING METHODS

## Basic

  1. What does `startsWith()` do?
  2. What does `endsWith()` do?
  3. What does `includes()` do?
  4. What does `repeat()` do?
  5. What is a template literal? What character is used to define it?
  6. What is string interpolation? How is it written in template literals?
  7. What does `String.raw()` do?

## Intermediate

  1. Write code that checks if `"JavaScript"` starts with `"Java"`.
  2. Write code that checks if `"JavaScript"` ends with `"Script"`.
  3. Write code that checks if `"JavaScript"` includes `"Script"`.
  4. Write code that repeats `"ab"` 3 times.
  5. Rewrite the following using a template literal:
    ```js
    var name = "Brendan";
    console.log("Hello, " + name + "!");
    ```
  6. Rewrite using template literals:
    ```js
    var a = 10, b = 10;
    console.log("The sum of " + a + " and " + b + " is " + (a + b));
    ```
  7. Write a multi-line string using template literals.

## Advanced

  1. Explain tagged templates. Write a tag function that logs literals and values.
  2. Write a tag function that converts the interpolated string to uppercase.
  3. What does `String.raw` return for `"Hello\nWorld"`? Compare with a normal template literal.
  4. Explain `String.fromCodePoint()` and give an example.
  5. Compare the case-sensitivity of `startsWith()`, `endsWith()`, and `includes()`.
  6. Write a function using `startsWith`, `endsWith`, and `includes` that validates a URL (e.g., starts with `https://`, includes a `.`, and ends with a valid TLD).
  7. Predict the output:
    ```js
    var str = "hello world!!!";
    console.log(str.startsWith("hello"));
    console.log(str.endsWith("world"));
    console.log(str.includes("lo wo"));
    console.log("ab".repeat(3));
    ```

---

# PART U: DEBUGGING & PREDICTION QUESTIONS

## Debugging

  1. Find and fix the error:
    ```js
    let x = 10;
    let x = 20;
    console.log(x);
    ```
  2. Find and fix the error:
    ```js
    const PI = 3.14;
    PI = 3.14159;
    ```
  3. Find and fix the error:
    ```js
    function add(a, b = 10, c) {
      return a + b + c;
    }
    ```
  4. Find and fix the error:
    ```js
    function sum(...params, extra) {
      return params.length;
    }
    ```
  5. Find and fix the error:
    ```js
    var arr = new Array(4);
    for (var i = 0; i <= arr.length; i++) {
      arr[i] = i * 2;
    }
    ```
  6. Find and fix the error:
    ```js
    const obj = { a: 1, b: 2 };
    delete obj;
    ```
  7. Find and fix the error:
    ```js
    let message = "Hello;
    console.log(message);
    ```
  8. Identify the issue:
    ```js
    var a = 10;
    var result = a < 10 && a > 5;
    console.log(a > 10 && a > 5);
    ```
  9. Identify the issue with this event handler:
    ```html
    <button onclick="sayHello()">Click</button>
    <script>
      sayHello = function() { alert("Hi"); };
    </script>
    ```
 10. Explain why this loop does not modify the original array:
    ```js
    const arr = [1, 2, 3];
    for (let x of arr) {
      x = x * 2;
    }
    console.log(arr);
    ```

## Prediction

  1. Predict the output:
    ```js
    var x = 10;
    function test() {
      console.log(x);
      var x = 20;
    }
    test();
    ```
  2. Predict the output:
    ```js
    for (var i = 0; i < 3; i++) {
      setTimeout(function() { console.log(i); }, 0);
    }
    ```
  3. Predict the output:
    ```js
    for (let i = 0; i < 3; i++) {
      setTimeout(function() { console.log(i); }, 0);
    }
    ```
  4. Predict the output:
    ```js
    function Person(name) {
      this.name = name;
    }
    var p1 = new Person("Alice");
    var p2 = Person("Bob");
    console.log(p1.name);
    console.log(p2);
    ```
  5. Predict the output:
    ```js
    const s1 = Symbol("hi");
    const s2 = Symbol.for("hi");
    console.log(Symbol.keyFor(s1));
    console.log(Symbol.keyFor(s2));
    ```
  6. Predict the output:
    ```js
    console.log(typeof Symbol());
    console.log(Symbol("a") === Symbol("a"));
    ```
  7. Predict the output:
    ```js
    const x = 10;
    {
      const x = 20;
      console.log(x);
    }
    console.log(x);
    ```
  8. Predict the output:
    ```js
    console.log("5" + 3);
    console.log("5" - 3);
    console.log(5 + "3");
    ```
  9. Predict the output:
    ```js
    var a = 1;
    {
      var a = 2;
    }
    console.log(a);
    ```
 10. Predict the output:
    ```js
    var arr = [10, 20, 30];
    console.log(arr.includes(20));
    console.log(arr.includes(40));
    ```
 11. Predict the output:
    ```js
    var str = "JavaScript";
    console.log(str.startsWith("Java"));
    console.log(str.startsWith("java"));
    console.log(str.includes("Script"));
    console.log(str.endsWith("Script"));
    ```
 12. Predict the output:
    ```js
    var name = "Tom";
    console.log(`Hello, ${name}! The length of your name is ${name.length}.`);
    ```
 13. Predict the output:
    ```js
    console.log(String.raw`Hello\nWorld`);
    console.log(`Hello\nWorld`);
    ```
 14. Predict the output:
    ```js
    const x = 5;
    function test() {
      const x = 10;
      return () => x + 5;
    }
    console.log(test()());
    ```
 15. Predict the output:
    ```js
    var obj = { a: 1, b: 2, c: 3 };
    var { a, ...rest } = obj;
    console.log(a);
    console.log(rest);
    ```

---

# PART V: CODING CHALLENGES (Apply Topics 1–20)

## Challenge 1: FizzBuzz with ES6 Features

Write a `fizzBuzz` function that:

- Uses a `for` loop with `let`.
- Prints "Fizz" for multiples of 3, "Buzz" for multiples of 5, "FizzBuzz" for multiples of both.
- Uses an arrow function to determine the output.
- Uses template literals for output.

## Challenge 2: Array Utilities Using `const` and Arrow Functions

Create the following using `const` and arrow functions:

- `double(arr)` — returns a new array with each element doubled.
- `filterEven(arr)` — returns only even numbers.
- `sum(arr)` — returns the sum of all elements.
- `average(arr)` — returns the average.

## Challenge 3: String Utilities

Write a module-like set of functions using `const`:

- `capitalize(str)` — capitalizes the first letter.
- `reverse(str)` — reverses a string.
- `isPalindrome(str)` — checks if a string is a palindrome.
- `countVowels(str)` — counts vowels.
- `truncate(str, length)` — truncates a string with `"..."`.

## Challenge 4: Object Manipulation

Given:

```js
const employees = [
  { name: "Alice", dept: "Engineering", salary: 90000 },
  { name: "Bob", dept: "Marketing", salary: 60000 },
  { name: "Charlie", dept: "Engineering", salary: 95000 },
  { name: "Dave", dept: "Sales", salary: 55000 },
];
```

Using object destructuring, `const`, `let`, and arrow functions:

- Filter employees by department.
- Calculate the total salary.
- Find the highest-paid employee.
- Return an array of `{ name, salary }` objects using `map()`.

## Challenge 5: Default Parameters and Spread

Write a function:

```js
function createUser(firstName, lastName, age = 18, ...hobbies) { ... }
```

- Return an object with the user's details.
- Default `age` to 18.
- Use rest parameters for `hobbies`.

## Challenge 6: Symbols and Classes

Create a `BankAccount` class:

- Uses a `Symbol` for the private balance property.
- Has `deposit()` and `withdraw()` methods.
- Uses a getter to expose the balance.
- Uses `const` for the class name.

## Challenge 7: Template Literal Debugger

Write a function that uses tagged template literals to log:

- The literal parts of the template.
- The interpolated values.
- The raw strings using `.raw`.

## Challenge 8: Mini Accounting Calculator

Build a page with:

- A form using `onsubmit` event.
- A `prompt()` to ask for an amount.
- `alert()` and `confirm()` for confirmations.
- Cookie storage to remember the last value.
- Page redirection after saving.
- A print button using `window.print()`.

## Challenge 9: Report Generator

Create a function:

```js
function generateReport(data, ...columns) { ... }
```

- Use a `switch` statement to format each column type.
- Use `startsWith`/`endsWith`/`includes` for validation.
- Use `String.raw` to generate the report text without escape processing.
- Return a `Symbol`-keyed hidden metadata object.

## Challenge 10: Complete ES6 Utility Library

Build a mini library exposing:

- `const`-based version string.
- `Number` utilities (isEven, isOdd, isPositive).
- `String` utilities (isEmail, isURL, isPhone).
- `Array` utilities (chunk, unique, flatten).
- `Object` utilities (pick, omit, deepClone).
- Export using a module pattern (based on your knowledge of ES6 modules).

---

# PART W: SHORT ANSWER / CONCEPTUAL QUESTIONS

  1. Explain why `const` does not make the assigned object fully immutable.
  2. What are the differences between `var`, `let`, and `const`? Provide a summary table.
  3. Why are arrow functions not suitable for methods that use `this`?
  4. Why are rest parameters preferable to the old `arguments` object?
  5. Explain the difference between `Symbol()` and `Symbol.for()`.
  6. What are the advantages of template literals over string concatenation?
  7. Why is block scope useful for loops?
  8. Why is `for...of` preferred over `for...in` for arrays?
  9. Explain the difference between `null` and `undefined` in the context of default parameters.
 10. Why might `Number.isNaN()` be more reliable than the global `isNaN()`?

---

# ANSWER KEY GUIDANCE

- **Basic questions** — answerable from direct definitions/examples in the notes.
- **Intermediate questions** — require applying the concepts (writing functions, predicting outputs).
- **Advanced questions** — require deep understanding (TDZ, hoisting edge cases, scope leakage, security, best practices).
- **Debugging** — identify the erroneous line and describe the fix.
- **Prediction** — output values and a one-line explanation.
- **Coding challenges** — should produce working code using the topics learned.

---

**Total: 375 questions** across 23 sections + 10 coding challenges — designed to reinforce all concepts from Topics 1–20.

Good luck! Work through these methodically, and test each code snippet in Node.js or your browser console.

# ES6 Notes: Topics 1–4

---

# Topic 1: ES6 – Overview

## 1.1 What is ECMAScript?

- **ECMAScript (ES)** is a scripting language specification standardized by ECMAScript International (formerly ECMA).
- It is used by applications to enable **client-side scripting**.
- The specification is influenced by programming languages like Self, Perl, Python, and Java.
- Languages governed by this specification include **JavaScript**, **JScript**, and **ActionScript**.

## 1.2 JavaScript Background

- Developed by **Brendan Eich** at Netscape Communications Corporation in **1995**.
- Originally named **Mocha**, briefly **LiveScript**, then officially renamed **JavaScript**.
- It is a scripting language executed by the browser (client-side).
- Used in conjunction with HTML to develop responsive web pages.

## 1.3 New Features in ES6

ES6 introduced major language enhancements:

| Feature | Description |
| --------- | ------------- |
| Constants | `const` for read-only references |
| Block Scope | `let` for block-level scoping |
| Arrow Functions | Concise function syntax |
| Extended Parameter Handling | Default parameters, rest parameters, spread operator |
| Template Literals | String interpolation with backticks |
| Extended Literals | Binary (`0b`) and octal (`0o`) literals |
| Enhanced Object Properties | Shorthand property and method syntax |
| Destructuring Assignment | Extract values from arrays/objects |
| Modules | `import` / `export` |
| Classes | `class` keyword, inheritance, `super` |
| Iterators | `for...of`, `Symbol.iterator` |
| Generators | `function*` with `yield` |
| Collections | `Map`, `Set`, `WeakMap`, `WeakSet` |
| New Built-in Methods | `Number.isNaN()`, `Array.from()`, etc. |
| Promises | Async programming with `Promise` |

## 1.4 ECMAScript Versions

| Edition | Version | Release Year | Notes |
| --------- | --------- | -------------- | ------- |
| 1 | ECMAScript 1 | 1997 | First edition |
| 2 | ECMAScript 2 | 1998 | Minor changes for ISO/IEC 16262 |
| 3 | ECMAScript 3 | 1999 | Language enhancements |
| 4 | ECMAScript 4 | — | Release plan dropped; features split between ES5 and ES6 |
| 5 | ECMAScript 5 | 2009 | Major update (strict mode, JSON, etc.) |
| 5.1 | ECMAScript 5.1 | 2011 | Minor changes for ISO/IEC 16262:2011 |
| 6 | ECMAScript 2015 / ES6 | 2015 | Major update (this tutorial's focus) |
| 7 | ECMAScript 2016 / ES7 | 2016 | Minor update |
| 8 | ECMAScript 2017 / ES8 | 2017 | Async/await, etc. |
| 9 | ECMAScript 2018 / ES9 | 2018 | Async generators, rest/spread for objects, etc. |

---

# Topic 2: ES6 – Environment

## 2.1 Local Environment Setup

To write and test JavaScript/ES6, you need:

1. **Text Editor** — for writing source code.
   - Examples: Windows Notepad, Notepad++, Emacs, Vim/Vi, Visual Studio Code, Brackets.
   - Source files typically have `.js` extension.

2. **Node.js** — open-source, cross-platform runtime for server-side JavaScript.
   - Required to run JavaScript without browser support.
   - Uses Google **V8 JavaScript engine**.
   - Available at: <https://nodejs.org/en/download>

## 2.2 Installing Node.js

### Windows

1. Download and run the `.msi` installer.
2. Verify installation: `node -v` in terminal (e.g., `v4.2.3`).

### Mac OS X

1. Download the pre-compiled binary package from nodejs.org.
2. Install from `.dmg` — installs both **node** and **npm** (Node Package Manager).

### Linux

- Install dependencies: Ruby ≥ 1.8.6, GCC ≥ 4.2, Homebrew/Linuxbrew.
- Then install Node.js and npm.

## 2.3 Integrated Development Environments (IDEs)

### Visual Studio Code (VS Code)

- Open-source IDE from Microsoft.
- Available for Mac OS X, Linux, Windows.
- Download: <https://code.visualstudio.com>
- Features: syntax highlighting, debugging, integrated terminal, extensions.
- Right-click file → **Open in Command Prompt** to run Node scripts.

### Brackets

- Free, open-source editor for web development by Adobe.
- Available for Linux, Windows, Mac OS X.
- Download: <http://brackets.io>
- Supports **Brackets Shell** extension for running shell commands within the editor.

---

# Topic 3: ES6 – Syntax

## 3.1 Program Components

A JavaScript program is composed of:

- **Variables** — named memory blocks that store values.
- **Literals** — constant/fixed values (e.g., numbers, strings).
- **Operators** — symbols that define how operands are processed.
- **Keywords** — words with special meaning in the language.
- **Modules** — reusable code blocks.
- **Comments** — used to improve readability; ignored by the engine.
- **Identifiers** — names for variables, functions, etc.

## 3.2 Keywords (Common)

`break`, `case`, `catch`, `continue`, `default`, `delete`, `do`, `else`, `finally`, `for`, `function`, `if`, `in`, `instanceof`, `new`, `return`, `switch`, `this`, `throw`, `try`, `typeof`, `var`, `void`, `while`, `with`, `let`, `const`, `class`, `export`, `import`, `super`, `extends`, `static`, `yield`, `async`, `await`, etc.

## 3.3 Identifiers – Rules

- Can include letters, digits, underscores (`_`), and dollar signs (`$`).
- **Cannot begin with a digit.**
- Cannot include special symbols except `_` and `$`.
- Cannot be a **keyword**.
- Must be **unique**.
- **Case-sensitive**.
- Cannot contain spaces.

| Valid Identifiers | Invalid Identifiers |
| ------------------- | --------------------- |
| `firstName` | `first-name` (hyphen) |
| `first_name` | `1number` (starts with digit) |
| `num1` | `#result` (special symbol) |
| `$result` | `first name` (space) |

## 3.4 Whitespace and Line Breaks

- ES6 ignores spaces, tabs, and newlines.
- You can format and indent code freely for readability.
- Example:

  ```js
  console.log("hello world")
  console.log("we are learning ES6")
  ```

## 3.5 Case Sensitivity

- JavaScript is **case-sensitive**: `firstName` and `firstname` are different identifiers.

## 3.6 Semicolons

- Semicolons are **optional** in JavaScript, but recommended.
- Multiple statements on a single line **must** be separated by semicolons:

  ```js
  console.log("hello"); console.log("world");
  ```

## 3.7 Comments

- **Single-line:** `// comment`
- **Multi-line:** `/* comment */`

```js
// This is a single-line comment
/*
  This is a
  multi-line comment
*/
```

## 3.8 Your First JavaScript Code

```js
var message = "Hello World"
console.log(message)
```

- Line 1: declares a variable named `message`.
- Line 2: prints the variable's value to the console.

## 3.9 Executing the Code (with Node.js)

1. Save file as `Test.js`.
2. Open terminal/command prompt in the file's directory.
3. Run: `node Test.js`
4. Output:

   ```
   Hello World
   ```

## 3.10 Strict Mode

- Introduced in ES5, **strict mode** enforces stricter parsing and error handling.
- Enable for entire script:

  ```js
  "use strict";
  v = "Hi! I'm a strict mode script!"; // ERROR: Variable v is not declared
  ```

- Enable for a function only:

  ```js
  v = 15; // allowed (non-strict)
  function f1() {
    "use strict";
    var v = "Hi! I'm a strict mode script!";
  }
  ```

- In strict mode:
  - Undeclared variables throw errors.
  - Assigning to read-only properties throws errors.
  - `delete` on non-deletable properties throws errors.
  - Duplicate parameter names are not allowed.
  - `with` statement is not allowed.

## 3.11 ES6 and Hoisting

- **Hoisting** is JavaScript's default behavior of moving **declarations** to the top of the current scope (function or script).
- Applies to **variables** and **functions**.
- Allows using a component before it is declared.
- **Not applicable in strict mode** for variables (temporal dead zone with `let`/`const`).
- Example:

  ```js
  console.log(company); // undefined (hoisted, but not initialized)
  var company = "TutorialsPoint";
  console.log(company); // TutorialsPoint
  ```

---

# Topic 4: ES6 – Variables

## 4.1 What is a Variable?

- A **variable** is a "named space in memory" that stores values.
- Acts as a **container** for values in a program.
- Variable names are called **identifiers**.

### Naming Rules (same as identifiers)

- Cannot be keywords.
- Can contain letters and numbers.
- Cannot contain spaces or special characters except `_` and `$`.
- Cannot begin with a number.

## 4.2 Type Syntax

A variable must be **declared** before use.

### ES5 (Traditional)

```js
var variable_name;
var variable_name = value;
```

### ES6 introduces

- `let` — block-scoped variable.
- `const` — block-scoped read-only reference.

### Example

```js
var name = "Tom";
console.log("The value in the variable is: " + name);
// Output: The value in the variable is: Tom
```

## 4.3 JavaScript and Dynamic Typing

- JavaScript is **untyped** / **dynamically typed**.
- A variable can hold a value of **any data type**.
- The type can **change during execution**.
- No need to specify the type at declaration.
- Example:

  ```js
  var x = 10;      // number
  x = "hello";     // now a string — allowed
  ```

## 4.4 Variable Scope

Traditionally (ES5), JavaScript has two scopes:

1. **Global Scope** — accessible from anywhere in the code.
2. **Local (Function) Scope** — accessible only within the function where declared.

### Example

```js
var num = 10;           // global
function test() {
  var num = 100;        // local
  console.log("value of num in test() " + num);  // 100
}
console.log("value of num outside test() " + num); // 10
test();
```

- Inside the function, the local `num` shadows the global `num`.
- Outside, the global `num` is used.

ES6 introduces a third scope:

1. **Block Scope** — restricts access to the block `{ }` in which the variable is declared.

## 4.5 `let` and Block Scope

- The `let` keyword allows the script to restrict access to the **nearest enclosing block**.
- Unlike `var`, `let` is **not hoisted** in the same way (temporal dead zone).
- Redeclaration within the same block throws an error.

### Example

```js
"use strict"
function test() {
  var num = 100;
  console.log("value of num in test() " + num); // 100
  {
    console.log("Inner Block begins");
    let num = 200;
    console.log("value of num : " + num); // 200
  }
}
test();
```

**Output:**

```
value of num in test() 100
Inner Block begins
value of num : 200
```

## 4.6 `let` vs `var` — Redeclaration

### With `var`

```js
var no = 10;
var no = 20;
console.log(no); // 20 (no error)
```

### With `let`

```js
let no = 10;
let no = 20;
console.log(no); // SyntaxError: Identifier 'no' has already been declared
```

## 4.7 `let` and Block-Level Safety

If you try to declare a `let` variable twice **within the same block**, it throws an error:

```js
let balance = 5000;
console.log(typeof balance); // number

let balance = { message: "hello" }; // ERROR: Identifier 'balance' has already been declared
```

## 4.8 `let` and Multiple Blocks

The same `let` variable name can be used in **different block scopes** without conflict:

```js
let count = 100;

for (let count = 1; count <= 10; count++) {
  console.log("count value inside loop is ", count); // 1 to 10
}

console.log("count value after loop is", count); // 100

if (count == 100) {
  let count = 50;
  console.log("count inside if block", count); // 50
}

console.log(count); // 100
```

**Output:**

```
count value inside loop is 1
...
count value inside loop is 10
count value after loop is 100
count inside if block 50
100
```

- Each block has its own independent `count`.

## 4.9 The `const` Keyword

- Creates a **read-only reference** to a value.
- The variable identifier **cannot be reassigned**.
- **Block-scoped**, like `let`.
- **Cannot be redeclared**.
- **Requires an initializer** (must be assigned at declaration).

### Rules

1. Constants cannot be reassigned.
2. A constant cannot be redeclared.
3. A constant requires an initializer.
4. The **value** assigned to a `const` is **mutable** (for objects/arrays).

### Example

```js
const x = 10;
x = 12; // ERROR: Assignment to constant variable
```

## 4.10 Constants are Immutable

```js
let income = 100000;
const INTEREST_RATE = 0.08;

income += 50000; // allowed (let is mutable)
console.log("changed income value is ", income); // 150000

INTEREST_RATE += 0.01; // ERROR: Assignment to constant variable
```

## 4.11 `const` and Arrays

- You **can** mutate the contents of a `const` array (push, pop, etc.).
- You **cannot** reassign the array to a new array.

```js
const DEPT_NOS = [10, 20, 30, 50];
DEPT_NOS.push(40);
console.log('dept numbers is ', DEPT_NOS); // [10, 20, 30, 50, 40]

const EMP_IDS = [1001, 1002, 1003];
EMP_IDS = [2001, 2002, 2003]; // ERROR: Assignment to constant variable
```

## 4.12 The `var` Keyword (Legacy)

- Used before ES6.
- **Function-scoped**, not block-scoped.
- Variables declared with `var` are **hoisted** to the top of their function/script and initialized to `undefined`.

## 4.13 `var` and Hoisting

```js
console.log(company); // undefined (hoisted)
var company = "TutorialsPoint";
console.log(company); // TutorialsPoint
```

**Output:**

```
undefined
TutorialsPoint
```

## 4.14 `var` and Block Scope

Variables declared with `var` do **not** have block scope — they leak out of loops and `if` blocks:

```js
for (var i = 1; i <= 5; i++) {
  console.log(i);
}
console.log("after the loop i value is " + i); // 6
```

**Output:**

```
1
2
3
4
5
after the loop i value is 6
```

## 4.15 `var` and Block-Level Safety

Declaring the same variable twice with `var` in the same block does **not** throw an error (unlike `let`):

```js
var balance = 5000;
console.log(typeof balance); // number

var balance = { message: "hello" };
console.log(typeof balance); // object
```

**Output:**

```
number
object
```

This can lead to **unexpected logical errors** at runtime.

## 4.16 Summary: `var` vs `let` vs `const`

| Feature | `var` | `let` | `const` |
| --------- | ------- | ------- | --------- |
| Scope | Function scope | Block scope | Block scope |
| Hoisting | Yes (initialized to `undefined`) | Yes (but TDZ — cannot access before declaration) | Yes (but TDZ) |
| Redeclaration | Allowed | Not allowed in same block | Not allowed |
| Reassignment | Allowed | Allowed | Not allowed |
| Initializer required | No | No | Yes |
| Mutability of value | Yes | Yes | Value is mutable for objects/arrays; binding is immutable |

---

# Key Takeaways (Topics 1–4)

1. **ES6 (ECMAScript 2015)** is a major update to JavaScript, introducing `let`, `const`, arrow functions, classes, modules, promises, and more.
2. **Node.js** allows running JavaScript outside the browser using the V8 engine.
3. **JavaScript syntax** is case-sensitive, semicolons are optional but recommended, and comments improve readability.
4. **Strict mode** (`"use strict"`) enforces stricter error handling.
5. **Hoisting** moves declarations to the top; `var` is hoisted and initialized to `undefined`, while `let`/`const` are hoisted but in a "temporal dead zone."
6. **Variables** in ES6 can be declared with `var` (function-scoped), `let` (block-scoped, reassignable), or `const` (block-scoped, not reassignable).
7. **Dynamic typing** means variables can hold values of any type and change type at runtime.
8. **Block scope** (`let`/`const`) prevents variables from leaking out of loops and conditionals, improving code safety.

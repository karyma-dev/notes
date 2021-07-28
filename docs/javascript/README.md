# Javascript

JavaScript, often abbreviated as JS, is a programming language that conforms to the ECMAScript specification. JavaScript is high-level, often just-in-time compiled, and multi-paradigm. It has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.

Data Types

- Primitive

  - String
  - Number
  - Boolean
  - Null
  - Undefined

- Non-Primitive Types
  - Array
  - Objects
  - Function

## Concepts

### [Try/Catch](https://www.w3schools.com/js/js_errors.asp)

- Used whenever you want to hide errors from user
- When you want to produce custom errors for your user
- Used where you suspect erros will occur that are beyond your control

```js
try {
  // Block of code to try
} catch (err) {
  // Block of code to handle errors
} finally {
  // Block of code to be executed regardless of the try / catch result
}
```

### Scope

- Block scope, Function scope, Global Scope
  - Before ES6 javascript only had function and global scope
-

### Hoisting

- All declaration gets moved to the top of their respective scope
- Only declaration gets hoisted not the initialization
- Good practice to declare variables at the top of their scope since new developers coming from another language may not know about the behavior of hoisting

### Strict Mode

- Cannot use variables or object without declaring it
- Cannot delete variables, object, functions or undeletable property
- Cannot use duplicate parameters
- Cannot use octals
- Cannot write to a read-only or get-only property
- eval cannot be used as a variable
- Cannot use `with` statement
- `this` in the global scope will return undefined

### JSON

- Can be written as Objects or Array, must be strings
- JSON.parse() convert from string to javascript object

### Performance

- Reduce activity in loops by placing variable outside of loops
- Reduce DOM activity, accessing the DOM can be very slow

### Best Practices

- Avoid global variables, `==`, `new`, `eval()`
- Initalize variables when you declare them
- Declare arrays and objects with const
- Don't use new Object()
  - Use `""` instead of `new String()`
  - Use `0` instead of `new Number()`
  - Use `false` instead of `new Boolean()`
  - Use `{}` instead of `new Object()`
  - Use `[]` instead of `new Array()`
  - Use `/()/` instead of `new RegExp()`
  - Use `function (){}` instead of `new Function()`
- Settings defaults for your parameters
- End switch statements with default even if theres no need for it

### Tricky Parts

- Floats
  - All programming languages including javascript have difficulties with precise floating point values because all numbers are stored as 64-bits floating point numbers(floats)
  - To solve this multiply it by 10 then divide 10
- Undefined is not the same as null
- Trailing commas in objects and arrays will crash IE 8

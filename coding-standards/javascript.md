# JavaScript Coding Standards

This document outlines the standards for writing clean and maintainable JavaScript code. By following these guidelines, we can ensure that our codebase is consistent, readable, and easy to work with.

## General Guidelines

- **Code Formatting:** We use Prettier for automatic code formatting. This ensures a consistent style across the entire codebase and avoids debates over stylistic choices.
- **Modern JavaScript:** Use modern JavaScript features (ES6+) when they are supported across all target browsers. Avoid deprecated APIs and browser-specific prefixes.

## Variables

- **Declaration:** Use `const` for variables that are not reassigned and `let` for variables that are. Avoid using `var` to prevent issues with scope.
- **Naming:** Variable names should be in `camelCase`, descriptive, and avoid abbreviations. For example, `userProfile` is better than `usrPrfl`.
- **One Declaration per Line:** Declare each variable on its own line.

```javascript
// Good
const itemCount = 10;
let isActive = true;

// Bad
var itemCount = 10, isActive = true;
```

## Strings

- **Quotes:** Use single quotes for strings, unless you need to use a single quote within the string, in which case double quotes are acceptable.
- **Template Literals:** Use template literals for strings that require interpolation or span multiple lines.

```javascript
// Good
const greeting = `Hello, ${name}!`;

// Bad
const greeting = "Hello, " + name + "!";
```

## Functions

- **Declaration:** Use function declarations instead of function expressions for named functions.
- **Arrow Functions:** Use arrow functions for anonymous functions (e.g., callbacks), but avoid them for methods where `this` context is important.
- **Parameters:** Avoid reassigning function parameters. If you need to modify a parameter, create a local variable.

```javascript
// Good
function getUser(id) {
  // ...
}

// Good
const numbers = [1, 2, 3];
const doubled = numbers.map(n => n * 2);
```

## Control Structures

- **Braces:** Always use braces for `if`, `for`, `while`, and other control structures, even if the body is a single line. This improves readability and prevents errors.
- **Equality:** Use the strict equality operator (`===`) and strict inequality operator (`!==`) instead of their loose counterparts (`==` and `!=`).

```javascript
// Good
if (isValid) {
  // ...
}

// Bad
if (isValid) doSomething();
```

## Comments

- **Clarity:** Write clear and concise comments that explain the "why" of the code, not the "what".
- **Single-Line:** Use `//` for single-line comments.
- **JSDoc:** Use JSDoc for documenting functions, including their parameters and return values.

```javascript
// Good
// Recalculate the total price to account for discounts.
const totalPrice = calculatePrice(items, discounts);
```

## Modules

- **ES Modules:** Use ES modules (`import`/`export`) for all new JavaScript code. Avoid CommonJS (`require`/`module.exports`).

```javascript
// Good
import { User } from './models';

export function getUser(id) {
  // ...
}
```
